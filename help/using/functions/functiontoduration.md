---
product: adobe campaign
title: toDuration
description: 瞭解函式toDuration
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 77f068fa-678e-49a4-b45f-843c3287390a
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 3%

---

# toDuration {#toDuration}

將引數值轉換為持續時間。 如需資料型別的詳細資訊，請參閱 [此頁面](../expression/data-types.md).

## 類別

轉換

## 函式語法

`toDuration(<parameter>)`

## 參數

| 參數 | 說明 |
|--- |--- |
| 字串 | 以ISO-8601持續時間格式PnDTnHnMn.nS為基礎的格式，將天數視為24小時 |
| 整數 | 毫秒數 |

如果字串運算式：接受的格式是以ISO-8601期間格式PnDTnHnMn.nS為基礎，而天數則視為24小時。

字串以選用的符號開頭，以ASCII負號或正號表示。 如果為負值，則整個期間都會被否定。 ASCII字母「P」是下一個大寫或小寫。 然後會有四個區段，每個區段包含一個數字和一個尾碼。 區段的ASCII尾碼為&quot;D&quot;、&quot;H&quot;、&quot;M&quot;及&quot;S&quot;，分別代表日、小時、分鐘及秒，可使用大寫或小寫。 尾碼必須依序出現。 ASCII字母「T」必須在小時、分鐘或秒區段的第一個專案（如果有的話）之前出現。 四個區段中的至少一個必須存在，如果存在「T」，則在「T」之後必須至少有一個區段。 每個區段的數字部分必須包含一個或多個ASCII數字。 數字可以以ASCII負號或正號為前置詞。 必須分析的天數、小時數和分鐘數。 秒數必須剖析為以及選用的分數。 小數點可以是點或逗號。 分數部分可能有0到9位數。

## 簽章與傳回型別

`toDuration(<string>)`

`toDuration(<integer>)`

傳回持續時間。

## 範例

`toDuration("PT10H")`

傳回10小時的持續時間。

`toDuration("PT4S")`

傳回4s的持續時間。

`toDuration(4000)`

傳回4s的持續時間。
