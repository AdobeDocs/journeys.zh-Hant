---
product: adobe campaign
title: inLastYears
description: 了解LastYears中的功能
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 95ca3d7d-2340-4378-9af4-aa1188bed614
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 18%

---

# inLastYears {#inLastYears}

如果指定的date或dateTime介於現在和現在之間 — 差值年，則返回true。

## 類別

Date

## 函式語法

`inLastYears(<dateTime>,<delta>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 日期時間 | dateTime |
| delta | 整數 |

## 簽名和返回類型

`inLastYears(<dateTime>,<integer>)`

傳回布林值。

## 範例

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4)`

傳回true。
