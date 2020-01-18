---
title: distinctWithNull
description: 瞭解distinctWithNull函式
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

---


# distinctWithNull {#distinctWithNull}

傳回清單的不同值。 如果清單至少有一個null值，則傳回的清單中會有null值。

## 類別

清單

## 函式語法

`distinctWithNull(<parameter>)`

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

`distinctWithNull(<listInteger>)`

傳回整數清單。

`distinctWithNull(<listDecimal>)`

傳回小數位清單。

`distinctWithNull(<listString>)`

傳回字串清單。

`distinctWithNull(<listDateTimeOnly>)`

傳回不考慮時區的日期時間清單。

`distinctWithNull(<listDateTime>)`

傳回datetimes清單。

`distinctWithNull(<listBoolean>)`

返回布爾值清單。

`distinctWithNull(<listDuration>)`

傳回持續時間清單。

## 範例

`distinctWithNull([10,2,10,null])`

傳 [回10、2、null]
