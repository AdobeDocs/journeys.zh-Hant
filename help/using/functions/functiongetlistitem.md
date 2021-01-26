---
product: adobe campaign
solution: Journey Orchestration
title: getListItem
description: 瞭解gstListItem函式
translation-type: tm+mt
source-git-commit: 5539ea0e8f124896f5599dba63babaa3e5b0229b
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 3%

---


# getListItem {#gestListItem}

傳回指定索引處的清單項目。

## 類別

清單

## 函式語法

`getListItem(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 清單 | listString |
| 清單 | listBoolean |
| 清單 | listInteger |
| 清單 | listDecimal |
| 清單 | listDuration |
| 清單 | listDateTime |
| 清單 | listDateTimeOnly |
| 索引 | 整數 |

## 簽名和傳回類型

`getListItem(<listInteger>,<index>)`

傳回整數清單。

`getListItem(<listDecimal>,<index>)`

傳回小數位清單。

`getListItem(<listString>,<index>)`

傳回字串清單。

`getListItem(<listDateTimeOnly>,<index>)`

傳回不考慮時區的日期時間清單。

`getListItem(<listDateTime>,<index>)`

傳回datetimes清單。

`getListItem(<listBoolean>,<index>)`

返回布爾值清單。

`getListItem(<listDuration>,<index>)`

傳回持續時間清單。

## 範例

`getListItem([10, 2, 3], 1)`

傳回&quot;2&quot;

`getListItem(["A", "B", "C"], 3)`
傳回&quot;C&quot;

事件欄位為event.appVersion的範例（含值）:&quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

傳回`["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

傳回&quot;20&quot;