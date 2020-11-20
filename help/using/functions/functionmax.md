---
product: adobe campaign
solution: Journey Orchestration
title: max
description: 瞭解函式max
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 4%

---

# max{#max}

傳回一組運算式中的最大值，以清單或兩個運算式的形式提供。 忽略空值。

## 類別

彙總

## 函式語法

`max(<parameter>)`

## 參數

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* 持續時間
* 整數
* 小數點
* dateTime
* dateTimeOnly

## 簽名和傳回的類型

`max(<listDuration>)`

傳回持續時間。

`max(<listInteger>)`

傳回持續時間。

`max(<listDateTimeOnly>)`

返回不考慮時區的日期時間。

`max(<listDateTime>)`

返回日期時間。

`max(<listDecimal>)`

傳回小數。

`max(<decimal>,<decimal>)`

傳回小數。

`max(<duration>,<duration>)`

傳回持續時間。

`max(<dateTime>,<dateTime>)`

返回日期時間。

`max(<dateTimeOnly>,<dateTimeOnly>)`

返回不考慮時區的日期時間。

`max(<integer>,<integer>)`

傳回整數。

## 範例

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

傳回10。

`max([10,null,8])`

傳回10。
