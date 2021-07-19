---
product: adobe campaign
title: min
description: 了解函式主要
feature: 歷程
role: Data Engineer
level: Experienced
exl-id: 7e13a08c-c51a-4d40-a3e2-ef70bd3edca5
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 7%

---

# min {#min}

傳回一組運算式中的最小值，以清單或兩個運算式的形式提供。 忽略Null值。

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
* 小數
* dateTime
* dateTimeOnly

## 簽名和返回的類型

`min(<listDuration>)`

傳回持續時間。

`min(<listInteger>)`

傳回持續時間。

`min(<listDateTimeOnly>)`

返回日期時間，而不考慮時區。

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

返回日期時間，而不考慮時區。

`min(<integer>,<integer>)`

傳回整數。

## 範例

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

返回3。

`min([10,null,8])`

傳回8。
