---
product: adobe campaign
solution: Journey Orchestration
title: inNextHours
description: 瞭解inNextHours的函式
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%

---


# inNextHours {#inNextHours}

如果指定date或dateTime介於現在和現在+增量小時之間，則傳回true。

## 類別

日期

## 函式語法

`inNextHours(<dateTime>,<delta>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 日期時間 | dateTime |
| δ | 整數 |

## 簽名和傳回類型

`inNextHours(<dateTime>,<integer>)`

傳回布林值。

## 範例

`inNextHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

傳回true。
