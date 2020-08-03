---
title: now
description: 立即瞭解此函式
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
source-git-commit: a0db4d65218861b71d35f83ccf2d15e25a1597e8
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 10%

---


# now {#now}

以日期時間格式傳回目前日期。 有關資料類型的詳細資訊，請參閱 [](../expression/data-types.md)。

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