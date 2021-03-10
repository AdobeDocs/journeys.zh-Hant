---
product: adobe campaign
solution: Journey Orchestration
title: now
description: 立即瞭解此函式
feature: 旅程
role: 資料工程師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 11%

---


# now {#now}

以日期時間格式傳回目前日期。 有關資料類型的詳細資訊，請參閱[此頁](../expression/data-types.md)。

## 類別

日期

## 函式語法

`now(<parameter>)`

## 參數

| 參數 | 說明 |
|--- |--- |
| 字串 |  |

## 簽名和傳回類型

`now()`

`now("<timeZone id>")`

傳回dateTime。

## 範例

`now()`

傳回2019-06-03T06:30Z。

`toString(now())`

傳回&quot;2019-06-03T06:30Z&quot;

`now("Europe/Paris")`

傳回2019-06-03T08:30+02:00。