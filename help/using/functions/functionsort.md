---
product: adobe campaign
title: sort
description: 瞭解函式排序
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 9%

---

# 排序 {#sort}

按自然順序對值或對象清單進行排序。

## 類別

清單

## 函式語法

`sort(<parameters>)`

## 參數

| 參數 | 類型 | 說明 |
|-----------|------------------|------------------|
| 清單排序 | listString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly或listObject | 清單進行排序。 對於listObject，它必須是欄位引用。 |
| keyAttributeName | 字串 | 此參數僅用於listObject。 給定清單對象中的屬性名稱用作排序的鍵。 |
| 排序順序 | 布林值 | 升序(true)或降序(false) |

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

`sort(<listObject>,<string>,<boolean>)`

返回對象清單。

## 範例

`sort(["A", "C", "B"], true)`

傳回 `["A","B","C"]`.

`sort([1, 3, 2], false)`

傳回 `[3, 2, 1]`.

