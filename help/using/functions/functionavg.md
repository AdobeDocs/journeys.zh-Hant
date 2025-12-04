---
product: adobe campaign
title: avg
description: 瞭解函式avg
feature: Journeys
role: Developer
level: Experienced
exl-id: 6c9f3a5d-20b4-4c0a-b17f-5221f5db51be
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 13%

---

# avg {#avg}

傳回一組運算式中的平均值（以清單或兩個運算式形式提供）。 會忽略Null值。


## 類別

彙總

## 函式語法

`avg(<parameter>)`

## 參數

支援的型別：

* listInteger
* listDecimal
* 小數
* 整數

## 簽章與傳回型別

`avg(<listInteger>)`

`avg(<listDecimal>)`

`avg(<decimal>,<decimal>)`

`avg(<decimal>,<integer>)`

`avg(<integer>,<decimal>)`

`avg(<integer>,<integer>)`

傳回小數。

## 範例

`avg(@{BarBeacon.inventory},5)`

`avg([10,3,8])`

傳回7.0。

`avg(10.2, 3)`

傳回6.6。
