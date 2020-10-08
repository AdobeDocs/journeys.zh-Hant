---
title: sort
description: 瞭解函式排序
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 10%

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

返回 `["A","B","C"]`。

`sort([1, 3, 2], false)`

返回 `[3, 2, 1]`。
