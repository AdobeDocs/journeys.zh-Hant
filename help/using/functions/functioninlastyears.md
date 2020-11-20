---
product: adobe campaign
solution: Journey Orchestration
title: inLastYears
description: 瞭解LastYears中的功能
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%

---


# inLastYears {#inLastYears}

如果指定的date或dateTime介於現在和現在- delta年，則傳回true。

## 類別

日期

## 函式語法

`inLastYears(<dateTime>,<delta>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 日期時間 | dateTime |
| δ | 整數 |

## 簽名和傳回類型

`inLastYears(<dateTime>,<integer>)`

傳回布林值。

## 範例

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4))`

傳回true。
