---
product: adobe campaign
solution: Journey Orchestration
title: sort
description: 瞭解函式排序
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 11%

---


# sort {#sort}

按自然順序對值清單進行排序。 第一個引數是值的清單，第二個是布林值，指出排序是遞增(true)或遞減(false)。

## 類別

清單

## 函式語法

`sort(<parameters>)`

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
| 布林值 | 布林值 |

## 簽名和傳回的類型

`sort(<listInteger>,<boolean>)`

傳回整數清單。

`sort(<listDecimal>,<boolean>)`

傳回小數位清單。

`sort(<listString>,<boolean>)`

傳回字串清單。

`sort(<listDateTimeOnly>,<boolean>)`

傳回不考慮時區的日期時間清單。

`sort(<listDateTime>,<boolean>)`

傳回datetimes清單。

`sort(<listBoolean>,<boolean>)`

返回布爾值清單。

## 範例

`sort(["A", "C", "B"], true)`

傳回`["A","B","C"]`。

`sort([1, 3, 2], false)`

傳回`[3, 2, 1]`。
