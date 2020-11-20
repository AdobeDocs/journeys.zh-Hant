---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: 瞭解inSegment的函式
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 6%

---


# inSegment {#inSegment}

檢查個人是否屬於指定區段。

區段名稱必須是字串常數。 它不能是欄位引用或表達式。

區段是在 [Adobe Experience Platform中定義](https://platform.adobe.com/segment/overview)。 運算式編輯器提供自動完成的區段清單。

>[!NOTE]
>
>您最多可擷取100個區段。

## 類別

Adobe Experience Platform

## 函式語法

`inSegment(<parameter>)`

## 參數

| 參數 | 說明 | 類型 |
|--- |--- |--- |
| 區段 | 區段名稱 | `<string>` |

## 簽名和傳回的類型

`inSegment(<string>)`

傳回布林值。

## 範例

`inSegment("men over 50")`

說明：

如果歷程例 **[!UICONTROL true]** 項中的個人屬於名為「50歲以上的男性」的Adobe Experience Platform區段，則函式會傳回 **[!UICONTROL false]** 。
