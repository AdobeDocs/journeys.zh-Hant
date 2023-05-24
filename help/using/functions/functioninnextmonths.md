---
product: adobe campaign
title: inNextMonths
description: 瞭解NextMonths中的函式
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b5e8d514-a24d-42a2-b422-ec5d6617048a
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inNextMonths {#inNextMonths}

如果給定日期或dateTime介於現在和現在+增量月份之間，則返回true。

## 類別

日期

## 函式語法

`inNextMonths(<dateTime>,<delta>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 日期時間 | 日期時間 |
| 三角 | 整數 |

## 簽名和返回的類型

`inNextMonths(<dateTime>,<integer>)`

返回布爾值。

## 範例

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4)`

返回true。
