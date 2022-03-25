---
product: adobe campaign
title: inNextDays
description: 瞭解NextDays中的函式
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 47d31b56-b0ed-426d-bd79-3db3e441454b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 18%

---

# 在下一天 {#inNextDays}

如果給定日期或dateTime介於現在和現在+增量天之間，則返回true。

## 類別

日期

## 函式語法

`inNextDays(<dateTime>,<delta>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 日期時間 | 日期時間 |
| 三角 | 整數 |

## 簽名和返回的類型

`inNextDays(<dateTime>,<integer>)`

返回布爾值。

## 範例

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

返回true。
