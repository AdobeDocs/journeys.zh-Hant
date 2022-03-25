---
product: adobe campaign
title: 條件指令（如果，則，else）
description: 瞭解條件指令
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 48fb4944-5b78-4ccd-9b9b-ffe0719e7c21
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 0%

---

# 條件指令（如果，則，else） {#section_cdz_lsk_w3b}

在高級編輯器中支援條件指令（如果，則為else）。 它允許定義更複雜的表達式。 它由下列元素組成：

* **[!UICONTROL if]**:要首先評估的條件。
* **[!UICONTROL then]**:條件評估結果為真時要計算的表達式。
* **[!UICONTROL else]**:條件評估結果為false時要計算的表達式。

>[!NOTE]
>
>所有表達式的周圍都需要括弧。

```json
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` 必須返回 **布爾**。

`<expression2>` 和 `<expression3>` 必須具有相同類型或相容類型。 支援的簽名和返回的類型包括：

```json
boolean,boolean : boolean
dateTime,dateTime : dateTime
dateTimeOnly,dateTimeOnly : dateTimeOnly
decimal,integer : decimal
integer,decimal : integer
integer,decimal : decimal
duration,duration : duration
string,string : string
listBoolean,listBoolean : listBoolean
listDateTime,listDateTime : listDateTime
listDateTimeOnly,listDateTimeOnly : listDateTimeOnly
listDateOnly,listDateOnly : listDateOnly
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**使用狀況**

條件指令允許您通過減少條件活動數來優化行程工作流。 例如，在同一操作活動中，您只能使用一個條件表達式為欄位定義指定兩個替代方案。

操作活動的示例（對於條件指令的結果需要字串的欄位）:

```json
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
