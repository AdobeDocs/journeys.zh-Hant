---
product: adobe campaign
title: inLastHours
description: 瞭解LastHours中的函式
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 9baeb836-e029-4e19-b08e-7b7b5f27ff8f
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 17%

---

# 在最後時間 {#inLastHours}

如果給定日期時間介於現在和現在之間 — 增量小時數，則返回true。

## 類別

日期

## 函式語法

`inLastHours(<dateTime>,<delta>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 日期時間 | 日期時間 |
| 三角 | 整數 |

## 簽名和返回的類型

`inLastHours(<dateTime>,<integer>)`

返回布爾值。

## 範例

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4)`

返回true。

`inLastHours(@{MyEvent.timestamp}, 4)`

返回true。
