---
product: adobe campaign
solution: Journey Orchestration
title: getListItem
description: 瞭解gstListItem函式
feature: 旅程
role: 資料工程師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 4%

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