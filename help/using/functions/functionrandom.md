---
product: adobe campaign
title: random
description: 隨機了解函式
feature: 歷程
role: Data Engineer
level: Experienced
exl-id: c47dc5f0-ea69-4814-863b-e0e483ba7770
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 11%

---

# 隨機 {#random}

產生0到1之間的隨機數。

## 類別

數學

## 函式語法

`random(<parameters>)`

## 簽名和返回類型

`random()`

傳回小數。

## 範例

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

說明：如果成功率沒有值/為null，則會套用預設值，且會是介於0和1 * 100（表示0到100）之間的隨機數字。
