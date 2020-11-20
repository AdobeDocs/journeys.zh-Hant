---
product: adobe campaign
solution: Journey Orchestration
title: min
description: 瞭解函式min
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 4%

---


# min {#min}

傳回一組運算式中的最小值，以清單或兩個運算式的形式提供。 忽略空值。

## 類別

彙總

## 函式語法

`min(<parameters>)`

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

`min(<listDuration>)`

傳回持續時間。

`min(<listInteger>)`

傳回持續時間。

`min(<listDateTimeOnly>)`

返回不考慮時區的日期時間。

`min(<listDateTime>)`

返回日期時間。

`min(<listDecimal>)`

傳回小數。

`min(<decimal>,<decimal>)`

傳回小數。

`min(<duration>,<duration>)`

傳回持續時間。

`min(<dateTime>,<dateTime>)`

返回日期時間。

`min(<dateTimeOnly>,<dateTimeOnly>)`

返回不考慮時區的日期時間。

`min(<integer>,<integer>)`

傳回整數。

## 範例

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

返回3。

`min([10,null,8])`

返回8。
