---
product: adobe campaign
title: inNextYears
description: 瞭解下一年的功能
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8aab6f60-feba-4be2-9a32-ba4ed7f3d7de
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inNextYears {#inNextYears}

如果給定日期或dateTime介於現在和現在+增量年間，則返回true。

## 類別

日期

## 函式語法

`inNextYears(<dateTime>,<delta>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 日期時間 | 日期時間 |
| 三角 | 整數 |

## 簽名和返回的類型

`inNextYears(<dateTime>,<integer>)`

返回布爾值。

## 範例

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4)`

返回true。
