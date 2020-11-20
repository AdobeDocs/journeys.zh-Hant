---
product: adobe campaign
solution: Journey Orchestration
title: toString
description: 瞭解函式toString
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 4%

---


# toString {#toString}

根據參數值的類型將參數值轉換為字串值。 For more information on data types, refer to [this page](../expression/data-types.md).

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
