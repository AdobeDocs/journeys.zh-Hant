---
product: adobe campaign
title: distinct
description: 了解不同的函式
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 034e4d77-2f0e-4117-9fd4-b9e35ef71a39
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 15%

---

# 不重複 {#distinct}

返回清單的不同值，但不帶空值。

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

## 簽名和返回的類型

`distinct(<listInteger>)`

傳回整數清單。

`distinct(<listDecimal>)`

傳回小數清單。

`distinct(<listString>)`

傳回字串清單。

`distinct(<listDateTimeOnly>)`

返回不考慮時區的datetimes清單。

`distinct(<listDateTime>)`

返回datetimes清單。

`distinct(<listBoolean>)`

傳回布林值清單。

`distinct(<listDuration>)`

傳回持續時間清單。

## 範例

`distinct([10,2,10,null])`

傳回`[10, 2]`。
