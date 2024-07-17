---
product: adobe campaign
title: limit
description: 瞭解函式限制
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7e006660-1206-4b8a-9e5b-c6fbeee9cc8f
source-git-commit: 9f5ef0497227a370e2e1f4a62450611ae2e336b9
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 8%

---

# limit {#limit}

傳回清單的第一個或最後的N個元素。

## 類別

清單

## 函式語法

`limit(<parameters>)`

## 參數

| 參數 | 類型 | 說明 |
|-----------|------------------|------------------|
| listToProcess | listString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly或listObject | 要排序的清單。 對於listObject，它必須是欄位參考。 |
| numberofItems | 整數 | 要從指定清單傳回的專案數。 |
| firstOrLastItems | 布林值 | 此引數為選用（預設為true）。 true會傳回第一個專案。 false會傳回最後一個專案。 |

## 簽章與傳回的型別

`limit(<listString>,<integer>)`
`limit(<listString>,<integer>,<boolean>)`

傳回字串清單。

`limit(<listInteger>,<integer>)`
`limit(<listInteger>,<integer>,<boolean>)`

傳回整數清單。

`limit(<listDecimal>,<integer>)`
`limit(<listDecimal>,<integer>,<boolean>)`

傳回小數點清單。

`limit(<listBoolean>,<integer>)`
`limit(<listBoolean>,<integer>,<boolean>)`

傳回布林值清單。

`limit(<listDateOnly>,<integer>)`
`limit(<listDateOnly>,<integer>,<boolean>)`

傳回日期清單。

`limit(<listDateTimeOnly>,<integer>)`
`limit(<listDateTimeOnly>,<integer>,<boolean>)`

傳回日期時間清單，不考慮時區。

`limit(<listDateTime>,integer>)`
`limit(<listDateTime>,<integer>,<boolean>)`

傳回日期時間清單。

`limit(<listDuration>,<integer>)`
`limit(<listDuration>,<integer>,<boolean>)`

傳回持續時間清單。

`limit(<listObject>,<integer>)`
`limit(<listObject>,<integer>,<boolean>)`

傳回物件清單。

## 範例

`limit(["A", "B", "C", "D", "E"], 3)`

傳回`["A","B","C"]`。

`limit(["A", "B", "C", "D", "E"], 3, false)`

傳回`["C","D","E"]`。
