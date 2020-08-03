---
title: distict
description: 瞭解不同功能
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
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 13%

---


# distict {#distinct}

傳回不含空值之清單的不同值。

## 類別

清單

## 函式語法

`distinct(<parameter>)`

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

## 簽名和傳回的類型

`distinct(<listInteger>)`

傳回整數清單。

`distinct(<listDecimal>)`

傳回小數位清單。

`distinct(<listString>)`

傳回字串清單。

`distinct(<listDateTimeOnly>)`

傳回不考慮時區的日期時間清單。

`distinct(<listDateTime>)`

傳回datetimes清單。

`distinct(<listBoolean>)`

返回布爾值清單。

`distinct(<listDuration>)`

傳回持續時間清單。

## 範例

`distinct([10,2,10,null])`

傳回 `[10, 2]`。
