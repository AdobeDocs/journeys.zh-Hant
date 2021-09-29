---
product: adobe campaign
title: 篩選
description: 了解函式篩選器
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 729ee71e063ae73c7c10f20bb3a410c43cb75faf
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 8%

---

# 篩選{#filter}

傳回listObject，其物件的索引鍵屬性與指定索引鍵值之一相符。

## 類別

清單

## 函式語法

`filter(<parameters>)`

## 參數

| 參數 | 類型 | 說明 |
|-----------|------------------|------------------|
| listToFilter | listObject | 要篩選的對象清單。 它必須是欄位參考。 |
| keyAttributeName | 字串 | 屬性名稱（在給定清單的對象中），用作篩選的鍵 |
| keyValueList | list | 篩選的索引鍵值陣列 |

## 簽名和返回的類型

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

以下是傳入事件「myevent」中傳遞之有效負載的範例：

```
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

```
filter(
 @{myevent.productListItems},
 id", 
 ["product2", "product3", "product4"]
)
```

傳回包含兩個物件（ID為「product2」和「product3」）的listObject。
