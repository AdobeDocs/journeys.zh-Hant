---
product: adobe campaign
title: inLastMonths
description: 瞭解LastMonths中的函式
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ff8effa9-404a-482b-8842-a276f029e2ed
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inLastMonths {#inLastMonths}

如果給定日期或dateTime介於現在和現在之間 — 增量月份，則返回true。

## 類別

日期

## 函式語法

`inLastMonths(<dateTime>,<delta>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 日期時間 | 日期時間 |
| 三角 | 整數 |

## 簽名和返回的類型

`inLastMonths(<dateTime>,<integer>)`

返回布爾值。

## 範例

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4)`

返回true。
