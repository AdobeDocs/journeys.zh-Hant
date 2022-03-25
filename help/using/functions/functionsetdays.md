---
product: adobe campaign
title: setDays
description: 瞭解函式setDays
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: eee7bf61-9101-4959-aa93-27d0f221c517
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 12%

---

# 設定天數 {#setDays}

僅設定日期時間或日期時間的日期。 例如，如果要等到月中某一天，則可以強制該日。

## 類別

日期

## 函式語法

`setDays(<parameter>)`

## 參數

| 參數 | 類型 |
|--- |--- |
| 日期時間 | 日期時間 |
| 不考慮區域的日期時間 | 日期僅時間 |
| 天 | 整數 |

## 簽名和返回的類型

`setDays(<dateTime>,<days>)`

返回日期時間。

`setDays(<dateTimeOnly>,<days>)`

返回不考慮時區的日期時間。

## 範例

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

返回2010-12-25T01:11:00Z。

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
