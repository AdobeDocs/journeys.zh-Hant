---
product: adobe campaign
solution: Journey Orchestration
title: distict
description: 瞭解不同功能
feature: 旅程
role: 資料工程師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '87'
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

傳回`[10, 2]`。
