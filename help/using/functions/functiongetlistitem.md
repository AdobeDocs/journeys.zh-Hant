---
product: adobe campaign
title: getListItem
description: 了解函式gstListItem
feature: 歷程
role: Data Engineer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 18%

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
| 索引 | 整數 |

## 簽名和返回類型

`getListItem(<listInteger>,<index>)`

傳回整數清單。

`getListItem(<listDecimal>,<index>)`

傳回小數清單。

`getListItem(<listString>,<index>)`

傳回字串清單。

`getListItem(<listDateTimeOnly>,<index>)`

返回不考慮時區的datetimes清單。

`getListItem(<listDateTime>,<index>)`

返回datetimes清單。

`getListItem(<listBoolean>,<index>)`

傳回布林值清單。

`getListItem(<listDuration>,<index>)`

傳回持續時間清單。

## 範例

`getListItem([10, 2, 3], 1)`

傳回&quot;2&quot;

`getListItem(["A", "B", "C"], 3)`
傳回&quot;C&quot;

事件欄位為「event.appVersion」且具有值的範例：&quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

傳回 `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

傳回&quot;20&quot;
