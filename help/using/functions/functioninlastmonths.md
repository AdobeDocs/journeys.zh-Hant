---
product: adobe campaign
solution: Journey Orchestration
title: inLastMonths
description: 瞭解LastMonths中的函式
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

---


# inLastMonths {#inLastMonths}

如果指定的date或dateTime介於現在和現在- delta月份，則傳回true。

## 類別

日期

## 函式語法

`inLastMonths(<dateTime>,<delta>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 日期時間 | dateTime |
| δ | 整數 |

## 簽名和傳回類型

`inLastMonths(<dateTime>,<integer>)`

傳回布林值。

## 範例

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4))`

傳回true。
