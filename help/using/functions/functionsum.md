---
product: adobe campaign
title: sum
description: 瞭解函式總和
feature: Journeys
role: Developer
level: Experienced
exl-id: 04289d72-aade-4725-b1f5-47cf55e3a40b
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 13%

---

# sum {#sum}

傳回一組運算式的值總和。 會忽略Null值。

## 類別

彙總

## 函式語法

`sum(<parameters>)`

## 參數

* listInteger
* listDecimal
* 期間
* 整數
* 小數

## 簽章與傳回的型別

`sum(<listDecimal>)`

傳回小數。

`sum(<listInteger>)`

傳回整數。

`sum(<integer>,<integer>)`

傳回整數。

`sum(<decimal>,<decimal>)`

傳回小數。

## 範例

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

傳回21。

`sum([10.5,null,8.1])`

傳回18.6。
