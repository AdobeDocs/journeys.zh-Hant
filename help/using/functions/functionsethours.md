---
product: adobe campaign
solution: Journey Orchestration
title: setHours
description: 瞭解函式setHours
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 5%

---


# setHours {#setHours}

僅設定日期時間或日期時間的小時數。 例如，如果您想要等到明天某個小時，您可以強制該小時。

## 類別

日期

## 函式語法

`setHours(<parameter>)`

## 參數

| 參數 | 類型 |
|--- |--- |
| 日期時間 | dateTime |
| 不考慮時區的日期時間 | dateTimeOnly |
| 小時 | 整數 |

## 簽名和傳回類型

`setHours(<dateTime>,<hours>)`

返回日期時間。

`setHours(<dateTimeOnly>,<hours>)`

返回不考慮時區的日期時間。

## 範例

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4))`

傳回2010-12-12T04:11:00Z。

`setHours(nowWithDelta(1, "days"), 20)`

明天晚上8點回來。
