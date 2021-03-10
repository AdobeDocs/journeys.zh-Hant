---
product: adobe campaign
solution: Journey Orchestration
title: toString
description: 瞭解函式toString
feature: 旅程
role: 資料工程師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 5%

---


# toString {#toString}

根據參數值的類型將參數值轉換為字串值。 有關資料類型的詳細資訊，請參閱[此頁](../expression/data-types.md)。

## 類別

轉換

## 函式語法

`toString(<parameter>)`

## 參數

| 參數 | 說明 |
|--- |--- |
| dateTime | 以UTC日期格式轉換日期 |
| dateTimeOnly | 以UTC日期格式轉換日期 |
| 持續時間 | 轉換為相應的毫秒數，作為字串 |
| 時區 | 轉換為時區ID字串表示法(JODA ID) |
| 整數 | 轉換為值的字串表示（1變為&quot;1&quot;） |
| 小數點 | 轉換為值的字串表示法（1.5變成&quot;1.5&quot;） |
| 布林值 | 若為true，則將布林值轉換為&#39;true&#39;；若為false，則將布林值轉換為&#39;false&#39; |

## 簽名和傳回類型

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<timeZone>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

傳回字串。

## 範例

`toString(4)`

傳回&quot;4&quot;。
