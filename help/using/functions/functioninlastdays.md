---
product: adobe campaign
title: inLastDays
description: 瞭解LastDays中的函式
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 1fc29153-3554-4af1-bb2e-7bba53ffce69
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inLastDays {#inLastDays}

如果給定日期或dateTime介於現在和現在之間 — 增量天，則返回true。

## 類別

日期

## 函式語法

`inLastDays(<dateTime>,<delta>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 日期時間 | 日期時間 |
| 三角 | 整數 |

## 簽名和返回的類型

`inLastDays(<dateTime>,<integer>)`

返回布爾值。

## 範例

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4)`

返回true。
