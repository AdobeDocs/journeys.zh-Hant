---
product: adobe campaign
title: inNextHours
description: 瞭解NextHours中的函式
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 4bcbfdbc-fc95-4089-8abc-f9314dde2c06
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inNextHours {#inNextHours}

如果給定日期或dateTime介於現在和現在之間+增量小時數，則返回true。

## 類別

日期

## 函式語法

`inNextHours(<dateTime>,<delta>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 日期時間 | 日期時間 |
| 三角 | 整數 |

## 簽名和返回的類型

`inNextHours(<dateTime>,<integer>)`

返回布爾值。

## 範例

`inNextHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

返回true。
