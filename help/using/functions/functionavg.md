---
product: adobe campaign
solution: Journey Orchestration
title: avg
description: 瞭解函式平均值
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 8%

---


# avg {#avg}

傳回一組運算式中的平均值，以清單或兩個運算式的形式提供。 忽略空值。


## 類別

彙總

## 函式語法

`avg(<parameter>)`

## 參數

支援的類型：

* listInteger
* listDecimal
* 小數點
* 整數

## 簽名和傳回類型

`avg(<listInteger>)`

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

返回7.0。

`avg(10.2, 3)`

返回6.6。
