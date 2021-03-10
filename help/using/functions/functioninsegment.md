---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: 瞭解inSegment的函式
feature: 旅程
role: 資料工程師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 7%

---


# inSegment {#inSegment}

檢查個人是否屬於指定區段。

區段名稱必須是字串常數。 它不能是欄位引用或表達式。

區段定義於[Adobe Experience Platform](https://platform.adobe.com/segment/overview)中。 運算式編輯器提供自動完成的區段清單。

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

如果歷程例項中的個人屬於名為&quot;men over 50&quot;的Adobe Experience Platform區段，則函式會傳回&#x200B;**[!UICONTROL true]**，否則會傳回&#x200B;**[!UICONTROL false]**。
