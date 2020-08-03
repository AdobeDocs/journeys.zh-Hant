---
title: max
description: 瞭解函式max
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 4%

---

# max{#max}

傳回一組運算式中的最大值，以清單或兩個運算式的形式提供。 忽略空值。

## 類別

聚總

## 函式語法

`max(<parameter>)`

## 參數

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* 持續時間
* 整數
* 小數點
* dateTime
* dateTimeOnly

## 簽名和傳回的類型

`max(<listDuration>)`

傳回持續時間。

`max(<listInteger>)`

傳回持續時間。

`max(<listDateTimeOnly>)`

返回不考慮時區的日期時間。

`max(<listDateTime>)`

返回日期時間。

`max(<listDecimal>)`

傳回小數。

`max(<decimal>,<decimal>)`

傳回小數。

`max(<duration>,<duration>)`

傳回持續時間。

`max(<dateTime>,<dateTime>)`

返回日期時間。

`max(<dateTimeOnly>,<dateTimeOnly>)`

返回不考慮時區的日期時間。

`max(<integer>,<integer>)`

傳回整數。

## 範例

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

傳回10。

`max([10,null,8])`

傳回10。
