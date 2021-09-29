---
product: adobe campaign
title: getListItem
description: 了解函式gstListItem
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
source-git-commit: 5e2af021f1c82063fcc0d4e4b5edf13c57cc6c72
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 21%

---

# getListItem {#gestListItem}

返回給定索引處的清單項。

## 類別

清單

## 函式語法

`getListItem(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| list | listString |
| 清單 | listBoolean |
| 清單 | listInteger |
| 清單 | listDecimal |
| 清單 | listDuration |
| 清單 | listDateTime |
| 清單 | listDateTimeOnly |
| 清單 | listDateOnly |
| 索引 | 整數 |

## 簽名和返回類型

`getListItem(<listInteger>,<index>)`

傳回整數。

`getListItem(<listDecimal>,<index>)`

傳回小數。

`getListItem(<listString>,<index>)`

傳回字串。

`getListItem(<listDateTimeOnly>,<index>)`

返回日期時間，而不考慮時區。

`getListItem(<listDateTime>,<index>)`

返回日期時間。

`getListItem(<listBoolean>,<index>)`

傳回布林值。

`getListItem(<listDuration>,<index>)`

傳回持續時間。

## 範例

`getListItem([10, 2, 3], 1)`

傳回&quot;2&quot;

`getListItem(["A", "B", "C"], 2)`
傳回&quot;C&quot;

事件欄位為「event.appVersion」且具有值的範例：&quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

傳回 `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

傳回&quot;20&quot;
