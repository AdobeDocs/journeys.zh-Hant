---
product: adobe campaign
title: min
description: 瞭解函式min
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7e13a08c-c51a-4d40-a3e2-ef70bd3edca5
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 6%

---

# 分鐘 {#min}

返回一組表達式中的最小值，以清單或兩個表達式的形式給定。 忽略空值。

## 類別

彙總

## 函式語法

`min(<parameters>)`

## 參數

* listDuration（持續時間）
* listInteger
* 清單十進位
* 清單日期時間
* listDateTimeOnly
* listDateOnly
* 持續時間
* 整數
* 小數
* 日期時間
* 日期僅時間

## 簽名和返回的類型

`min(<listDuration>)`

返回持續時間。

`min(<listInteger>)`

返回持續時間。

`min(<listDateTimeOnly>)`

返回不考慮時區的日期時間。

`min(<listDateTime>)`

返回日期時間。

`min(<listDateOnly>)`

返回日期。

`min(<listDecimal>)`

返回十進位。

`min(<decimal>,<decimal>)`

返回十進位。

`min(<duration>,<duration>)`

返回持續時間。

`min(<dateTime>,<dateTime>)`

返回日期時間。

`min(<dateTimeOnly>,<dateTimeOnly>)`

返回不考慮時區的日期時間。

`min(<integer>,<integer>)`

返回整數。

## 範例

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

返回3。

`min([10,null,8])`

返回8。
