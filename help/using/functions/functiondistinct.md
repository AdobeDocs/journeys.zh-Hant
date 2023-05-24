---
product: adobe campaign
title: distinct
description: 瞭解不同的功能
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 034e4d77-2f0e-4117-9fd4-b9e35ef71a39
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 7%

---

# distinct {#distinct}

返回給定清單的不同值或對象。 忽略空項。

## 類別

清單

## 函式語法

`distinct(<parameters>)`

## 參數

| 參數 | 類型 | 說明 |
|-----------|------------------|------------------|
| 清單至進程 | listString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly或listObject | 要處理的清單。 對於listObject，它必須是欄位引用。 |
| keyAttributeName | 字串 | 此參數是可選的，且僅適用於listObject。 如果未提供該參數，則如果所有屬性具有相同的值，則對象被視為重複對象。 否則，如果給定屬性具有相同的值，則對象被視為重複對象。 |

## 簽名和返回的類型

`distinct(<listInteger>)`

返回整數清單。

`distinct(<listDecimal>)`

返回小數位清單。

`distinct(<listString>)`

返回字串清單。

`distinct(<listDateTimeOnly>)`

返回不考慮時區的日期時間清單。

`distinct(<listDateTime>)`

返回日期時間清單。

`distinct(<listDateOnly>)`

返回日期清單。

`distinct(<listBoolean>)`

返回布爾值清單。

`distinct(<listDuration>)`

返回持續時間清單。

`distinct(<listObject>)`

`distinct(<listObject>,<string>)`

返回對象清單。


## 範例

`distinct([10,2,10,null])`

傳回 `[10, 2]`.
