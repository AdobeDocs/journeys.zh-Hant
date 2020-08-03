---
title: setHours
description: 瞭解函式setHours
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c
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
