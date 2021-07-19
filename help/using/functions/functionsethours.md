---
product: adobe campaign
title: setHours
description: 了解函式setHours
feature: 歷程
role: Data Engineer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 12%

---

# setHours {#setHours}

僅設定日期時間或日期時間的小時數。 例如，如果您想要等到明天某個小時，您可以強制該小時。

## 類別

Date

## 函式語法

`setHours(<parameter>)`

## 參數

| 參數 | 類型 |
|--- |--- |
| 日期時間 | dateTime |
| 不考慮時區的日期時間 | dateTimeOnly |
| 小時 | 整數 |

## 簽名和返回類型

`setHours(<dateTime>,<hours>)`

返回日期時間。

`setHours(<dateTimeOnly>,<hours>)`

返回日期時間，而不考慮時區。

## 範例

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4))`

傳回2010-12-12T04:11:00Z。

`setHours(nowWithDelta(1, "days"), 20)`

明天晚上8點返回。
