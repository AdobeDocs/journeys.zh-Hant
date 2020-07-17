---
title: inSegment
description: 瞭解inSegment的函式
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 4%

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
