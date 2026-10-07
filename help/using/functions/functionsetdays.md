---
product: adobe campaign
title: setDays
description: 瞭解函式setDays
feature: Journeys
role: Developer
level: Experienced
exl-id: eee7bf61-9101-4959-aa93-27d0f221c517
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 13%
---
# setDays {#setDays}

僅設定日期時間或日期時間的日期。 例如，如果您要等到月份的某一天，則可以強制該天。

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

## 簽章與傳回型別

`setDays(<dateTime>,<days>)`

傳回日期時間。

`setDays(<dateTimeOnly>,<days>)`

傳回日期時間，不考慮時區。

## 範例

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

傳回2010-12-25T01:11:00Z。

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
