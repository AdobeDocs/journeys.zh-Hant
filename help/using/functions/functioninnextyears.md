---
product: adobe campaign
solution: Journey Orchestration
title: inNextYears
description: 瞭解NextYears中的功能
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

---


# inNextYears {#inNextYears}

如果指定的date或dateTime介於現在和現在+ delta年間，則傳回true。

## 類別

日期

## 函式語法

`inNextYears(<dateTime>,<delta>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 日期時間 | dateTime |
| δ | 整數 |

## 簽名和傳回類型

`inNextYears(<dateTime>,<integer>)`

傳回布林值。

## 範例

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4))`

傳回true。
