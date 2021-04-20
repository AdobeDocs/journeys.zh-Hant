---
product: adobe campaign
solution: Journey Orchestration
title: 條件式指令（若，則為else）
description: 瞭解條件式教學
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---


# 條件式指令(if, then, else){#section_cdz_lsk_w3b}

進階編輯器支援條件式指令（若然，則為else）。 它允許定義更複雜的表達式。 它由下列元素組成：

* **[!UICONTROL if]**:要先評估的條件。
* **[!UICONTROL then]**:條件評估結果為真時要評估的表達式。
* **[!UICONTROL else]**:條件評估結果為false時要評估的表達式。

>[!NOTE]
>
>所有運算式的周圍都需要括弧。

```
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` 必須返回布 **林**。

`<expression2>` 且 `<expression3>` 必須有相同的類型或相容類型。支援的簽名和傳回的類型包括：

```
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
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**使用情況**

條件式指令可讓您減少條件活動的數目，以最佳化歷程工作流程。 例如，在相同的動作活動中，您只能使用一個條件運算式，為欄位定義指定兩個替代項目。

動作活動的範例（對於需要字串作為條件式指令結果的欄位）:

```
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
