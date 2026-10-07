---
product: adobe campaign
title: 條件式指令(if， then， else)
description: 瞭解條件式指令
feature: Journeys
role: Developer
level: Experienced
exl-id: 48fb4944-5b78-4ccd-9b9b-ffe0719e7c21
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 25%
---
# 條件式指令(if， then， else) {#section_cdz_lsk_w3b}


>[!CAUTION]
>
>**正在尋找 Adobe Journey Optimizer**？ 按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}以取得 Journey Optimizer 文件。
>
>
>_本文件指的是已由 Journey Optimizer 取代的舊版 Journey Orchestration 資料。 如果您對 Journey Orchestration 或 Journey Optimizer 的存取權有任何疑問，請聯絡您的帳戶團隊。_


進階編輯器支援條件式指令(if， then， else)。 它可讓您定義更複雜的運算式。 它由下列元素組成：

* **[!UICONTROL if]**：要先評估的條件。
* **[!UICONTROL then]**：條件評估結果為true時要評估的運算式。
* **[!UICONTROL else]**：條件評估結果為false時要評估的運算式。

>[!NOTE]
>
>所有運算式都必須加上括弧。

```json
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>`必須傳回&#x200B;**布林值**。

`<expression2>`和`<expression3>`必須具有相同的型別或相容的型別。 支援的簽章和傳回的型別包括：

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

條件式指示可讓您透過減少條件活動的數量，將歷程工作流程最佳化。 例如，在相同動作活動中，您僅能使用一個條件運算式，即可為欄位定義指定兩個替代方案。

動作活動的範例（適用於預期字串為條件指令結果的欄位）：

```json
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
