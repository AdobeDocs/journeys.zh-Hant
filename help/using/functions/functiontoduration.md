---
product: adobe campaign
title: toDuration
description: 了解函式toDuration
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

將引數值轉換為持續時間。 如需資料類型的詳細資訊，請參閱 [本頁](../expression/data-types.md).

## 類別

轉換

## 函式語法

`toDuration(<parameter>)`

## 參數

| 參數 | 說明 |
|--- |--- |
| 字串 | 基於ISO-8601持續時間格式的格式PnDTnHnMn.nS，天數被認為恰好為24小時 |
| 整數 | 毫秒數 |

如果字串表達式：接受的格式基於ISO-8601持續時間格式PnDTnHnMn.nS，其天數被認為恰好為24小時。

字串以可選符號開頭，以ASCII負號或正號表示。 如果為負，則整個週期被否定。 ASCII字母「P」在大小寫中為下一個。 然後有四個區段，每個都由數字和尾碼組成。 各節的ASCII尾碼為「D」、「H」、「M」和「S」，代表日、小時、分鐘和秒，大小寫上接受。 尾碼必須按順序發生。 ASCII字母「T」必須在一小時、分鐘或秒區的第一個出現（如果有）之前出現。 四個部分中至少必須有一個，如果存在&quot;T&quot;，則&quot;T&quot;後面必須至少有一個部分。 每個節的數字部分必須包含一個或多個ASCII數字。 數字可以前置詞為ASCII負號或正號。 必須一併剖析天數、小時數和分鐘數。 必須剖析秒數以及選用的分數。 小數點可以是點或逗號。 小數部分可以具有0到9位數。

## 簽名和返回類型

`toDuration(<string>)`

`toDuration(<integer>)`

傳回持續時間。

## 範例

`toDuration("PT10H")`

傳回10小時的持續時間。

`toDuration("PT4S")`

傳回4秒的持續時間。

`toDuration(4000)`

傳回4秒的持續時間。
