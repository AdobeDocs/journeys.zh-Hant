---
product: adobe campaign
title: inLastYears
description: 瞭解函式inLastYears
feature: Journeys
role: Developer
level: Experienced
exl-id: 95ca3d7d-2340-4378-9af4-aa1188bed614
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
source-wordcount: '44'
ht-degree: 20%
---
# inLastYears {#inLastYears}

如果指定的日期或dateTime介於現在和現在之間 — 差異年份，則傳回true。

## 類別

日期

## 函式語法

`inLastYears(<dateTime>,<delta>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 日期時間 | dateTime |
| delta | 整數 |

## 簽章與傳回型別

`inLastYears(<dateTime>,<integer>)`

傳回布林值。

## 範例

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4)`

傳回true。
