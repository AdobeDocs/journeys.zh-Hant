---
product: adobe campaign
title: sort
description: 了解函式排序
feature: 歷程
role: Data Engineer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 17%

---

# 排序 {#sort}

以自然順序排序值清單。 第一個引數是值清單，第二個引數是布林值，指出排序是遞增(true)還是遞減(false)。

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

## 簽名和返回類型

`sort(<listInteger>,<boolean>)`

傳回整數清單。

`sort(<listDecimal>,<boolean>)`

傳回小數清單。

`sort(<listString>,<boolean>)`

傳回字串清單。

`sort(<listDateTimeOnly>,<boolean>)`

返回不考慮時區的datetimes清單。

`sort(<listDateTime>,<boolean>)`

返回datetimes清單。

`sort(<listBoolean>,<boolean>)`

傳回布林值清單。

## 範例

`sort(["A", "C", "B"], true)`

傳回 `["A","B","C"]`.

`sort([1, 3, 2], false)`

傳回 `[3, 2, 1]`.
