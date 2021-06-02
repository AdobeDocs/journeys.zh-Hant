---
product: adobe campaign
title: inLastDays
description: 了解LastDays中的函式
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 1fc29153-3554-4af1-bb2e-7bba53ffce69
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 13%

---

# inLastDays {#inLastDays}

如果指定的日期或dateTime介於現在和現在之間 — 差值天，則傳回true。

## 類別

日期

## 函式語法

`inLastDays(<dateTime>,<delta>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 日期時間 | dateTime |
| delta | 整數 |

## 簽名和返回類型

`inLastDays(<dateTime>,<integer>)`

傳回布林值。

## 範例

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4))`

傳回true。
