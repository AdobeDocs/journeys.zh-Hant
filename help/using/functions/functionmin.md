---
product: adobe campaign
title: min
description: 瞭解函式最小值
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7e13a08c-c51a-4d40-a3e2-ef70bd3edca5
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 7%

---

# min {#min}

傳回一組運算式中的最小值，以清單或兩個運算式形式提供。 會忽略Null值。

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
* listDateOnly
* 期間
* 整數
* 小數
* dateTime
* dateTimeOnly

## 簽章與傳回的型別

`min(<listDuration>)`

傳回持續時間。

`min(<listInteger>)`

傳回持續時間。

`min(<listDateTimeOnly>)`

傳回日期時間，不考慮時區。

`min(<listDateTime>)`

傳回日期時間。

`min(<listDateOnly>)`

傳回日期。

`min(<listDecimal>)`

傳回小數。

`min(<decimal>,<decimal>)`

傳回小數。

`min(<duration>,<duration>)`

傳回持續時間。

`min(<dateTime>,<dateTime>)`

傳回日期時間。

`min(<dateTimeOnly>,<dateTimeOnly>)`

傳回日期時間，不考慮時區。

`min(<integer>,<integer>)`

傳回整數。

## 範例

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

傳回3。

`min([10,null,8])`

傳回8。
