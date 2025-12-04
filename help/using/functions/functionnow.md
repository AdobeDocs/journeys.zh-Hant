---
product: adobe campaign
title: now
description: 立即瞭解函式
feature: Journeys
role: Developer
level: Experienced
exl-id: ab1f9efe-cbb7-4e3a-ace0-24f2fb6165cb
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 16%

---

# now {#now}

以日期時間格式傳回目前日期。 如需資料型別的詳細資訊，請參閱[此頁面](../expression/data-types.md)。

## 類別

日期

## 函式語法

`now(<parameter>)`

## 參數

| 參數 | 說明 |
|--- |--- |
| 字串 |  |

## 簽章與傳回型別

`now()`

`now("<timeZone id>")`

傳回日期時間。

## 範例

`now()`

傳回2019-06-03T06:30Z。

`toString(now())`

傳回「2019-06-03T06:30Z」

`now("Europe/Paris")`

傳回2019-06-03T08:30+02:00。
