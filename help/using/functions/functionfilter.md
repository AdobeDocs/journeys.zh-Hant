---
product: adobe campaign
title: 篩選
description: 瞭解函式篩選器
feature: Journeys
role: Developer
level: Experienced
exl-id: 3c1c188c-0ffd-44c5-b1b3-1758ed12235e
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 10%
---
# 篩選{#filter}

傳回listObject，其中物件的索引鍵屬性符合其中一個指定的索引鍵值。

## 類別

清單

## 函式語法

`filter(<parameters>)`

## 參數

| 參數 | 類型 | 說明 |
|-----------|------------------|------------------|
| listToFilter | listObject | 要篩選的物件清單。 它必須是欄位參考。 |
| keyAttributeName | 字串 | 指定清單物件中的屬性名稱，用來作為篩選的索引鍵 |
| keyValueList | list | 用於篩選的索引鍵值陣列 |

## 簽章與傳回的型別

`filter(listObject, string, listString)`

`filter(listObject, string, listInteger)`

`filter(listObject, string, listDecimal)`

`filter(listObject, string, listDateTime)`

`filter(listObject, string, listDateTimeOnly)`

`filter(listObject, string, listDateOnly)`

`filter(listObject, string, listDuration)`

`filter(listObject, string, listBoolean)`

傳回listObject。

## 範例

以下是在傳入事件「myevent」中傳遞的裝載範例：

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

您可以使用下列運算式：

```json
filter(
 @{myevent.productListItems},
 "id", 
 ["product2", "product3", "product4"]
)
```

傳回listObject，其中包含以&quot;product2&quot;和&quot;product3&quot;作為ID的兩個物件。
