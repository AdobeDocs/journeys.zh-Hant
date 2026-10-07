---
product: adobe campaign
title: now
description: 立即瞭解函式
feature: Journeys
role: Developer
level: Experienced
exl-id: ab1f9efe-cbb7-4e3a-ace0-24f2fb6165cb
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 15%
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
