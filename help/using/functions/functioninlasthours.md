---
product: adobe campaign
solution: Journey Orchestration
title: inLastHours
description: 瞭解inLastHours的函式
feature: 旅程
role: 資料工程師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 10%

---


# inLastHours {#inLastHours}

如果指定的日期時間介於現在和現在之間——增量小時，則返回true。

## 類別

日期

## 函式語法

`inLastHours(<dateTime>,<delta>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 日期時間 | dateTime |
| δ | 整數 |

## 簽名和傳回類型

`inLastHours(<dateTime>,<integer>)`

傳回布林值。

## 範例

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4))`

傳回true。

`inLastHours(@{MyEvent.timestamp}, 4)`

傳回true。
