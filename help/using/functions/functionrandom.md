---
product: adobe campaign
solution: Journey Orchestration
title: random
description: 瞭解隨機函式
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 5%

---


# random {#random}

產生0到1之間的隨機數。

## 類別

數學

## 函式語法

`random(<parameters>)`

## 簽名和傳回的類型

`random()`

傳回小數。

## 範例

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

說明：如果成功率沒有值/is null，則會套用預設值，且會是0到1 * 100（意指0到100）之間的隨機數。
