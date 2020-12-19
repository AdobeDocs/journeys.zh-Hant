---
product: adobe campaign
solution: Journey Orchestration
title: distinctWithNull
description: 瞭解distinctWithNull函式
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 11%

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

傳回[10, 2,null]
