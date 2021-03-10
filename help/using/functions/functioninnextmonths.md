---
product: adobe campaign
solution: Journey Orchestration
title: inNextMonths
description: 瞭解NextMonths中的函式
feature: 旅程
role: 資料工程師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

---


# inNextMonths {#inNextMonths}

如果指定的date或dateTime介於現在和現在+增量月份之間，則傳回true。

## 類別

日期

## 函式語法

`inNextMonths(<dateTime>,<delta>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 日期時間 | dateTime |
| δ | 整數 |

## 簽名和傳回類型

`inNextMonths(<dateTime>,<integer>)`

傳回布林值。

## 範例

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4))`

傳回true。
