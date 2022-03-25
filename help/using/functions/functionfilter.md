---
product: adobe campaign
title: 篩選
description: 瞭解函式篩選器
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3c1c188c-0ffd-44c5-b1b3-1758ed12235e
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 10%

---

# 篩選{#filter}

返回具有與給定鍵值之一匹配的鍵屬性的對象的listObject。

## 類別

清單

## 函式語法

`filter(<parameters>)`

## 參數

| 參數 | 類型 | 說明 |
|-----------|------------------|------------------|
| 清單到篩選器 | listObject | 要篩選的對象清單。 它必須是欄位引用。 |
| keyAttributeName | 字串 | 給定清單對象中的屬性名稱，用作篩選鍵 |
| keyValueList | list | 用於篩選的鍵值陣列 |

## 簽名和返回的類型

`filter(listObject, string, listString)`

`filter(listObject, string, listInteger)`

`filter(listObject, string, listDecimal)`

`filter(listObject, string, listDateTime)`

`filter(listObject, string, listDateTimeOnly)`

`filter(listObject, string, listDateOnly)`

`filter(listObject, string, listDuration)`

`filter(listObject, string, listBoolean)`

返回listObject。

## 範例

以下是傳入事件「myevent」中傳遞的負載示例：

```json
"productListItems": [{
   "id": "product1",
   "name": "the product 1",
   "price": 20
},{
   "id": "product2",
   "name": "the product 2",
   "price": 30
},{
   "id": "product3",
   "name": "the product 3",
   "price": 50
}]
```

可以使用以下表達式：

```json
filter(
 @{myevent.productListItems},
 "id", 
 ["product2", "product3", "product4"]
)
```

返回一個listObject，該對象包含兩個以&quot;product2&quot;和&quot;product3&quot;為id的對象。
