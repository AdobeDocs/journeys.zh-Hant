---
product: adobe campaign
title: avg
description: 瞭解函式avg
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 6c9f3a5d-20b4-4c0a-b17f-5221f5db51be
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
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
