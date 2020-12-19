---
product: adobe campaign
solution: Journey Orchestration
title: now
description: 立即瞭解此函式
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 10%

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