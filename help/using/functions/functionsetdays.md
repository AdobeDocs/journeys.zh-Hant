---
product: adobe campaign
solution: Journey Orchestration
title: setDays
description: 瞭解函式setDays
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 6%

---


# setDays {#setDays}

僅設定日期時間或日期時間的日期。 例如，如果您想要等到當月的某一天，則可強制該天。

## 類別

日期

## 函式語法

`setDays(<parameter>)`

## 參數

| 參數 | 類型 |
|--- |--- |
| 日期時間 | dateTime |
| 不考慮時區的日期時間 | dateTimeOnly |
| 天 | 整數 |

## 簽名和傳回類型

`setDays(<dateTime>,<days>)`

返回日期時間。

`setDays(<dateTimeOnly>,<days>)`

返回不考慮時區的日期時間。

## 範例

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

傳回2010-12-25T01:11:00Z。

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
