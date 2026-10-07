---
product: adobe campaign
title: max
description: 瞭解函式最大值
feature: Journeys
role: Developer
level: Experienced
exl-id: 116713e0-7bbd-4150-8495-f87034eafb5f
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
source-wordcount: '94'
ht-degree: 7%
---
# max{#max}

傳回一組運算式中的最大值，以清單或兩個運算式形式提供。 會忽略Null值。

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
* 期間
* 整數
* 小數
* dateTime
* dateTimeOnly

## 簽章與傳回的型別

`max(<listDuration>)`

傳回持續時間。

`max(<listInteger>)`

傳回持續時間。

`max(<listDateTimeOnly>)`

傳回日期時間，不考慮時區。

`max(<listDateTime>)`

傳回日期時間。

`max(<listDateOnly>)`

傳回日期。

`max(<listDecimal>)`

傳回小數。

`max(<decimal>,<decimal>)`

傳回小數。

`max(<duration>,<duration>)`

傳回持續時間。

`max(<dateTime>,<dateTime>)`

傳回日期時間。

`max(<dateTimeOnly>,<dateTimeOnly>)`

傳回日期時間，不考慮時區。

`max(<integer>,<integer>)`

傳回整數。

## 範例

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

傳回10。

`max([10,null,8])`

傳回10。
