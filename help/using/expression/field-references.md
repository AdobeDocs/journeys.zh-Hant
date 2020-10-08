---
title: 欄位參考
description: 瞭解進階運算式中的欄位參考
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 1%

---



# 欄位參考 {#concept_fkj_ll5_dgb}

欄位參考可附加至事件或欄位群組。 唯一有意義的資訊是欄位名稱及其路徑。

如果您在欄位中使用特殊字元，則需使用雙引號或簡單引號。 以下是需要引號的案例：

* 場以數字字元開頭
* 欄位開頭為&quot;-&quot;字元
* 欄位包含下列項目以外的其他項目： _a_-z _,_ A _-_ Z,0 _-Z_, _____9-Z,-Z,_

例如，若您的欄位是 _3h_: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

在運算式中，事件欄位被引用為&quot;@&quot;，資料來源欄位被引用為&quot;#&quot;。

語法顏色用於以視覺方式區分事件欄位（綠色）和欄位群組（藍色）。

**欄位參考的預設值**

預設值可與欄位名稱關聯。 語法如下：

```
// event field
@{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address, defaultValue: "example@adobe.com"}
```

>[!NOTE]
>
>欄位的類型和預設值必須相同。 例如，@{LobbyBeacon.endUserIDs。_experience.emailid.id, defaultValue :2}將無效，因為預設值是整數，而預期值應為字串。

**系列中欄位的參考**

系列中定義的元素會使用特定函式all、first和last來參考。 For more information, see [](../expression/collection-management-functions.md).

範例 :

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

**映射中定義的欄位的引用**

為了檢索映射中的元素，我們使用帶有給定鍵的輸入函式。 例如，根據所選的命名空間定義事件的索引鍵時，會使用它。 請參閱選擇命名空間。 For more information, see [](../event/selecting-the-namespace.md).

```
@{MyEvent.identityMap.entry('Email').first().id}
```

在此運算式中，我們會取得事件「IdentityMap」欄位的「電子郵件」索引鍵項目。 「電子郵件」項目是系列，我們會從中取用第一個元素中的「id」，使用「first()」。 For more information, see [](../expression/collection-management-functions.md).

**資料來源的參數值（資料來源動態值）**

如果您從外部資料來源選取需要呼叫參數的欄位，右側會出現新標籤，讓您指定此參數。 請參閱[](../expression/expressionadvanced.md)。

For more complex use cases, if you want to include the parameters of the data source in the main expression, you can define their values using the keyword _params_. 參數可以是任何有效的運算式，即使是來自其他資料來源，也包含其他參數。

>[!NOTE]
>
>當您在運算式中定義參數值時，右側的標籤會消失。

使用下列語法：

```
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**:資料來源的第一個參數的確切名稱。
* **`<params-1-value>`**:第一個參數的值。 它可以是任何有效的運算式。

範例:

```
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
