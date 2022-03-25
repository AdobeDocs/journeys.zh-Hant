---
product: adobe campaign
title: setHours
description: 瞭解函式setHours
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 8%

---

# 設定小時數 {#setHours}

僅設定日期時間或日期時間的小時數。 例如，如果您想等到明天某個小時，您可以強制該小時。

## 類別

日期

## 函式語法

`setHours(<parameter>)`

## 參數

| 參數 | 類型 |
|--- |--- |
| 日期時間 | 日期時間 |
| 不考慮區域的日期時間 | 日期僅時間 |
| 小時 | 整數 |

## 簽名和返回的類型

`setHours(<dateTime>,<hours>)`

返回日期時間。

`setHours(<dateTimeOnly>,<hours>)`

返回不考慮時區的日期時間。

## 範例

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

返回2010-12-12T04:11:00Z。

`setHours(nowWithDelta(1, "days"), 20)`

明天在8:XY PM（XY是當前時間評估時的分鐘）返回。 如果評估在凌晨2:45進行，則返回時間為晚8:45。
