---
product: adobe campaign
title: 欄位參考
description: 了解進階運算式中的欄位參考
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2f317306-9afd-4e9a-88b8-fc66102e1046
source-git-commit: e4a003656058ac7ae6706e22fd5162c9e875629a
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 3%

---

# 欄位參考 {#concept_fkj_ll5_dgb}

欄位參考可附加至事件或欄位群組。 唯一有意義的資訊是欄位名稱及其路徑。

如果您在欄位中使用特殊字元，則需要使用雙引號或簡單引號。 需要引號的情況如下：

* 欄位以數字字元開頭
* 欄位以&quot;-&quot;字元開頭
* 欄位包含下列項目以外的其他項目： _a_-_z_, _A_-_Z_, _0_-_9_, _ , _-_

例如，如果欄位為 _3h_: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```json
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

在運算式中，事件欄位被「@」引用，資料源欄位被「#」引用。

語法顏色可以視覺上區分事件欄位（綠色）和欄位群組（藍色）。

## 欄位參考的預設值

預設值可與欄位名稱關聯。 語法如下：

```json
// event field
@{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address, defaultValue: "example@adobe.com"}
```

>[!NOTE]
>
>欄位的類型和預設值必須相同。 例如， @{LobbyBeacon.endUserIDs。_experience.emailid.id, defaultValue :2}將無效，因為預設值為整數，而預期值應為字串。

範例：

```json
// for an event 'OrderEvent' having the following payload:
{
    "orderId": "12345"
}
 
expression example:
- @{OrderEvent.orderId}                                    -> "12345"
- @{OrderEvent.producdId, defaultValue : "not specified" } -> "not specified" // default value, productId is not a field present in the payload
- @{OrderEvent.productId}                                  -> null
 
 
// for an entity 'Profile' on datasource 'ACP' having fields person/lastName, with fetched data such as:
{
    "person": {
        "lastName":"Snow"
    },
    "emails": [
        { "email":"john.snow@winterfell.westeros" },
        { "email":"snow@thewall.westeros" }
    ]
}
 
expression examples:
- #{ACP.Profile.person.lastName}                 -> "Snow"
- #{ACP.Profile.emails.at(1).email}              -> "snow@thewall.westeros"
- #{ACP.Profile.person.age, defaultValue : -1}   -> -1 // default value, age is not a field present in the payload
- #{ACP.Profile.person.age}                      -> null
```

## 對集合內欄位的參考

系列中定義的元素會使用特定函式來參照 `all`, `first` 和 `last`. 如需詳細資訊，請參閱[本頁面](../expression/collection-management-functions.md)。

範例 :

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

## 對映射中定義的欄位的引用

### `entry` 函數

為了擷取地圖中的元素，我們使用包含指定鍵的登入函式。 例如，根據選取的命名空間定義事件的索引鍵時，會使用它。 請參閱選取命名空間。 如需詳細資訊，請參閱 [本頁](../event/selecting-the-namespace.md).

```json
@{MyEvent.identityMap.entry('Email').first().id}
```

在此運算式中，我們會取得事件「IdentityMap」欄位中「Email」索引鍵的項目。 「Email」項目是集合，我們會從中使用「first()」取得第一個元素中的「id」。 如需詳細資訊，請參閱 [本頁](../expression/collection-management-functions.md).

### `firstEntryKey` 函數

若要擷取地圖的第一個項目索引鍵，請使用 `firstEntryKey` 函式。

此範例顯示如何擷取特定清單訂閱者的第一個電子郵件地址：

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-email').subscribers.firstEntryKey()}
```

在此範例中，訂閱清單的名稱為 `daily-email`. 電子郵件地址定義為 `subscribers` 地圖，連結至訂閱清單地圖。

### `keys` 函數

若要擷取地圖的所有索引鍵，請使用 `keys` 函式。

此範例顯示如何針對特定設定檔擷取與特定清單訂閱者相關聯的所有電子郵件地址：

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-mail').subscribers.keys()
```

## 資料源的參數值（資料源動態值）

如果您從外部資料來源選取欄位，需要呼叫參數，右側會出現新索引標籤，讓您指定此參數。 請參閱[此頁面](../expression/expressionadvanced.md)。

對於更複雜的使用案例，如果您想將資料來源的參數納入主運算式中，則可以使用關鍵字定義其值 _params_. 參數可以是任何有效的運算式，即使來自另一個資料來源（也包含另一個參數）也是如此。

>[!NOTE]
>
>當您在運算式中定義參數值時，右側的索引標籤會消失。

使用下列語法：

```json
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**:資料來源中第一個參數的確切名稱。
* **`<params-1-value>`**:第一個參數的值。 它可以是任何有效的運算式。

範例：

```json
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
