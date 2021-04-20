---
product: adobe campaign
solution: Journey Orchestration
title: inLastDays
description: 瞭解LastDays中的函式
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

---


# inLastDays {#inLastDays}

如果指定date或dateTime介於現在和現在- delta天，則傳回true。

## 類別

日期

## 函式語法

`inLastDays(<dateTime>,<delta>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 日期時間 | dateTime |
| δ | 整數 |

## 簽名和傳回類型

`inLastDays(<dateTime>,<integer>)`

傳回布林值。

## 範例

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4))`

傳回true。
