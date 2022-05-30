---
product: adobe campaign
title: 限
description: 瞭解函式限制
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 7%

---

# 限 {#limit}

返回清單的第一個或最後一個N元素。

## 類別

清單

## 函式語法

`limit(<parameters>)`

## 參數

| 參數 | 類型 | 說明 |
|-----------|------------------|------------------|
| 清單至進程 | listString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly或listObject | 清單進行排序。 對於listObject，它必須是欄位引用。 |
| 項目數 | 整數 | 要從給定清單返回的項數。 |
| firstOrLastItems | 布林值 | 此參數是可選的（預設為true）。 true將返回第一個項。 false返回最後一個項。 |

## 簽名和返回的類型

`limit(<listString>,<integer>)`
`limit(<listString>,<integer>,<boolean>)`

返回字串清單。

`limit(<listInteger>,<integer>)`
`limit(<listInteger>,<integer>,<boolean>)`

返回整數清單。

`limit(<listDecimal>,<integer>)`
`limit(<listDecimal>,<integer>,<boolean>)`

返回小數位清單。

`limit(<listBoolean>,<integer>)`
`limit(<listBoolean>,<integer>,<boolean>)`

返回布爾值清單。

`limit(<listDateOnly>,<integer>)`
`limit(<listDateOnly>,<integer>,<boolean>)`

返回日期清單。

`limit(<listDateTimeOnly>,<integer>)`
`limit(<listDateTimeOnly>,<integer>,<boolean>)`

返回不考慮時區的日期時間清單。

`limit(<listDateTime>,integer>)`
`limit(<listDateTime>,<integer>,<boolean>)`

返回日期時間清單。

`limit(<listDuration>,<integer>)`
`limit(<listDuration>,<integer>,<boolean>)`

返回持續時間清單。

`limit(<listObject>,<integer>)`
`limit(<listObject>,<integer>,<boolean>)`

返回對象清單。

## 範例

`limit(["A", "B", "C", "D", "E"], 3)`

傳回 `["A","B","C"]`.

`limit(["A", "B", "C", "D", "E"], 3, false)`

傳回 `["C","D","E"]`.
