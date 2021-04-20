---
product: adobe campaign
solution: Journey Orchestration
title: toDuration
description: 瞭解函式toDuration
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 2%

---


# toDuration {#toDuration}

將參數值轉換為持續時間。 有關資料類型的詳細資訊，請參閱[此頁](../expression/data-types.md)。

## 類別

轉換

## 函式語法

`toDuration(<parameter>)`

## 參數

| 參數 | 說明 |
|--- |--- |
| 字串 | 基於ISO-8601持續時間格式PnDTnHnMn.nS的格式，其天數被認為恰好為24小時 |
| 整數 | 毫秒數 |

如果字串表達式：接受的格式基於ISO-8601持續時間格式PnDTnHnMn.nS，其天數被認為恰好為24小時。

字串以選用符號開頭，以ASCII負號或正號表示。 如果為負，則整個時段都會被否定。 ASCII字母&quot;P&quot;是大寫或小寫的下一個。 然後有四個部分，每個部分都由一個數字和一個尾碼組成。 區段的ASCII尾碼為&quot;D&quot;、&quot;H&quot;、&quot;M&quot;和&quot;S&quot;，以天、小時、分和秒為單位，以大寫或小寫為準。 尾碼必須按順序出現。 ASCII字母&quot;T&quot;必須發生在小時、分鐘或第二節的第一次出現（如果有）之前。 這四個區段中至少有一個必須存在，如果&quot;T&quot;存在，則&quot;T&quot;後面必須有至少一個區段。 每個部分的編號部分必須由一個或多個ASCII數字組成。 數字可以用ASCII負號或正號作為前置詞。 必須分析的天數、小時數和分鐘數。 秒數必須與可選分數一起解析。 小數點可以是點或逗號。 該小數部分可以具有從零到9位。

## 簽名和傳回類型

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
