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

將參數值轉換為持續時間。 有關資料類型的詳細資訊，請參閱 [此頁](../expression/data-types.md)。

## 類別

轉換

## 函式語法

`toDuration(<parameter>)`

## 參數

| 參數 | 說明 |
|--- |--- |
| 字串 | 基於ISO-8601持續時間格式PnDTnHnMn.nS的格式，天數被認為正好為24小時 |
| 整數 | 毫秒數 |

如果字串表達式：接受的格式基於ISO-8601持續時間格式PnDTnHnMn.nS，天數被認為恰好為24小時。

字串以可選符號開頭，用ASCII負或正符號表示。 如果為負，則整個週期被否定。 ASCII字母&quot;P&quot;是大寫或小寫的下一個。 然後是四個部分，每個部分都由一個數字和一個尾碼組成。 各節的ASCII尾碼為「D」、「H」、「M」和「S」，以天、小時、分鐘和秒為單位，大寫或小寫均接受。 尾碼必須按順序出現。 ASCII字母&quot;T&quot;必須出現在小時、分鐘或第二節的第一次出現（如果有）之前。 四個部分中至少必須有一個，如果存在&quot;T&quot;，則在&quot;T&quot;之後必須至少有一個部分。 每個節的編號部分必須由一個或多個ASCII數字組成。 該數字可以由ASCII負或正符號作前置詞。 必須隨時分析的天數、小時數和分鐘數。 秒數必須與可選分數一起分析到。 小數點可以是點或逗號。 小數部分可具有0至9位。

## 簽名和返回的類型

`toDuration(<string>)`

`toDuration(<integer>)`

返回持續時間。

## 範例

`toDuration("PT10H")`

返回持續時間10小時。

`toDuration("PT4S")`

返回4秒的持續時間。

`toDuration(4000)`

返回4秒的持續時間。
