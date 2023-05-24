---
product: adobe campaign
title: now
description: 立即瞭解該功能
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ab1f9efe-cbb7-4e3a-ace0-24f2fb6165cb
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 18%

---

# now {#now}

以日期時間格式返回當前日期。 有關資料類型的詳細資訊，請參閱 [此頁](../expression/data-types.md)。

## 類別

日期

## 函式語法

`now(<parameter>)`

## 參數

| 參數 | 說明 |
|--- |--- |
| 字串 |  |

## 簽名和返回的類型

`now()`

`now("<timeZone id>")`

返回dateTime。

## 範例

`now()`

返回2019-06-03T06:30Z。

`toString(now())`

返回「2019-06-03T06:30Z」

`now("Europe/Paris")`

返回2019-06-03T08:30+02:00。
