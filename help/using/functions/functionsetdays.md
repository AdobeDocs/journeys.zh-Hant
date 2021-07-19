---
product: adobe campaign
title: setDays
description: 了解函式setDays
feature: 歷程
role: Data Engineer
level: Experienced
exl-id: eee7bf61-9101-4959-aa93-27d0f221c517
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 13%

---

# setDays {#setDays}

僅設定日期時間或日期時間的日期。 例如，如果您想要等到當月的某一天，可以強制該天。

## 類別

Date

## 函式語法

`setDays(<parameter>)`

## 參數

| 參數 | 類型 |
|--- |--- |
| 日期時間 | dateTime |
| 不考慮時區的日期時間 | dateTimeOnly |
| 天 | 整數 |

## 簽名和返回類型

`setDays(<dateTime>,<days>)`

返回日期時間。

`setDays(<dateTimeOnly>,<days>)`

返回日期時間，而不考慮時區。

## 範例

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

傳回2010-12-25T01:11:00Z。

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
