---
product: adobe campaign
title: sort
description: 瞭解函式排序
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 16%

---

# 排序 {#sort}

按自然順序對值清單進行排序。 第一個參數是值清單，第二個參數是指示排序是升序(true)還是降序(false)的布爾值。

## 類別

清單

## 函式語法

`sort(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 清單 | 清單字串 |
| 清單 | list布爾 |
| 清單 | listInteger |
| 清單 | 清單十進位 |
| 清單 | listDuration（持續時間） |
| 清單 | 清單日期時間 |
| 清單 | listDateTimeOnly |
| 清單 | listDateOnly |
| 布爾型 | 布爾型 |

## 簽名和返回的類型

`sort(<listInteger>,<boolean>)`

返回整數清單。

`sort(<listDecimal>,<boolean>)`

返回小數位清單。

`sort(<listString>,<boolean>)`

返回字串清單。

`sort(<listDateTimeOnly>,<boolean>)`

返回不考慮時區的日期時間清單。

`sort(<listDateTime>,<boolean>)`

返回日期時間清單。

`sort(<listDateOnly>,<boolean>)`

返回日期清單。

`sort(<listBoolean>,<boolean>)`

返回布爾值清單。

## 範例

`sort(["A", "C", "B"], true)`

傳回 `["A","B","C"]`.

`sort([1, 3, 2], false)`

傳回 `[3, 2, 1]`.
