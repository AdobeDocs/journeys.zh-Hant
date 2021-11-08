---
product: adobe campaign
title: max
description: 了解函式最大值
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 116713e0-7bbd-4150-8495-f87034eafb5f
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 6%

---

# max{#max}

傳回一組運算式中的最大值，以清單或兩個運算式的形式提供。 忽略Null值。

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
* listDateOnly
* 持續時間
* 整數
* 小數
* dateTime
* dateTimeOnly

## 簽名和返回的類型

`max(<listDuration>)`

傳回持續時間。

`max(<listInteger>)`

傳回持續時間。

`max(<listDateTimeOnly>)`

返回日期時間，而不考慮時區。

`max(<listDateTime>)`

返回日期時間。

`max(<listDateOnly>)`

傳回日期。

`max(<listDecimal>)`

傳回小數。

`max(<decimal>,<decimal>)`

傳回小數。

`max(<duration>,<duration>)`

傳回持續時間。

`max(<dateTime>,<dateTime>)`

返回日期時間。

`max(<dateTimeOnly>,<dateTimeOnly>)`

返回日期時間，而不考慮時區。

`max(<integer>,<integer>)`

傳回整數。

## 範例

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

傳回10。

`max([10,null,8])`

傳回10。
