---
product: adobe campaign
solution: Journey Orchestration
title: inLastHours
description: 瞭解inLastHours的函式
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 8%

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
