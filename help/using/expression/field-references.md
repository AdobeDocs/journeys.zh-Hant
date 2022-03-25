---
product: adobe campaign
title: 欄位參考
description: 瞭解高級表達式中的欄位引用
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

欄位引用可以附加到事件或欄位組。 唯一有意義的資訊是欄位的名稱及其路徑。

如果在欄位中使用特殊字元，則需要使用雙引號或簡單引號。 以下是需要引用引號的情況：

* 欄位以數字字元開頭
* 欄位以&quot;-&quot;字元開頭
* 該欄位包含除以下內容之外的任何內容： _a_-_z_。 _A_-_Z_。 _0_-_9_, _-_

例如，如果欄位為 _3小時_: _#{OpenWeather.weatherData.rain。&#39;3h&#39;> 0_

```json
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

在表達式中，事件欄位與「@」一起引用，資料源欄位與「#」一起引用。

語法顏色用於直觀地區分事件欄位（綠色）和欄位組（藍色）。

## 欄位引用的預設值

預設值可以與欄位名關聯。 語法如下：

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
>欄位的類型和預設值必須相同。 例如，@{LobbyBeacon.endUserID。_experience.emailid.id，預設值：2}將無效，因為預設值是整數，而預期值應是字串。

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

## 對集合中欄位的引用

使用特定函式引用集合中定義的元素 `all`。 `first` 和 `last`。 如需詳細資訊，請參閱[本頁面](../expression/collection-management-functions.md)。

範例 :

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

## 對映射中定義的欄位的引用

### `entry` 函數

為了檢索映射中的元素，我們使用帶給定鍵的entry函式。 例如，在根據所選命名空間定義事件的鍵時使用它。 請參閱選擇命名空間。 有關詳細資訊，請參見 [此頁](../event/selecting-the-namespace.md)。

```json
@{MyEvent.identityMap.entry('Email').first().id}
```

在此表達式中，我們將獲取事件的「IdentityMap」欄位的「Email」鍵的條目。 「Email」條目是一個集合，我們從中使用「first()」獲取第一個元素中的「id」。 有關詳細資訊，請參見 [此頁](../expression/collection-management-functions.md)。

### `firstEntryKey` 函數

要檢索映射的第一個條目鍵，請使用 `firstEntryKey` 的子菜單。

此示例說明如何檢索特定清單的訂戶的第一個電子郵件地址：

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-email').subscribers.firstEntryKey()}
```

在本示例中，訂閱清單被命名 `daily-email`。 電子郵件地址被定義為 `subscribers` 映射，它連結到訂閱清單映射。

### `keys` 函數

要檢索到映射的所有鍵，請使用 `keys` 的子菜單。

此示例說明如何為特定配置檔案檢索與特定清單的訂戶關聯的所有電子郵件地址：

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-mail').subscribers.keys()
```

## 資料源的參數值（資料源動態值）

如果從外部資料源中選擇一個需要調用參數的欄位，則右側將顯示一個新頁籤，以便您指定此參數。 請參閱[此頁面](../expression/expressionadvanced.md)。

對於更複雜的使用情形，如果要在主表達式中包括資料源的參數，可以使用關鍵字定義其值 _帕拉_。 參數可以是任何有效的表達式，即使來自另一個資料源，該資料源也包含另一個參數。

>[!NOTE]
>
>在表達式中定義參數值時，右側的頁籤將消失。

使用以下語法：

```json
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**:資料源中第一個參數的準確名稱。
* **`<params-1-value>`**:第一個參數的值。 它可以是任何有效的表達式。

範例：

```json
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
