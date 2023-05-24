---
product: adobe campaign
title: sum
description: 瞭解函式和
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 04289d72-aade-4725-b1f5-47cf55e3a40b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 13%

---

# sum {#sum}

返回一組表達式的值之和。 忽略空值。

## 類別

彙總

## 函式語法

`sum(<parameters>)`

## 參數

* listInteger
* 清單十進位
* 持續時間
* 整數
* 小數

## 簽名和返回的類型

`sum(<listDecimal>)`

返回十進位。

`sum(<listInteger>)`

返回整數。

`sum(<integer>,<integer>)`

返回整數。

`sum(<decimal>,<decimal>)`

返回十進位。

## 範例

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

返回21。

`sum([10.5,null,8.1])`

返回18.6。
