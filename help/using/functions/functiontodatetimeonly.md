---
product: adobe campaign
solution: Journey Orchestration
title: toDateTimeOnly
description: 瞭解函式toDateTime
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 9%

---


# toDateTimeOnly{#toDateTimeOnly}

將參數值轉換為僅限日期時間的值。

## 類別

轉換

## 函式語法

`toDateTimeOnly(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| ISO-8601格式的日期時間 | 字串 |
| 日期時間 | dateTime |

## 簽名和傳回的類型

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

不考慮時區而返回日期時間。

## 範例

`toDateTimeOnly ("2016-08-18T23:17:59.123Z")`

傳回2016-08-18T23:17:59.123。

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
