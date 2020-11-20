---
product: adobe campaign
solution: Journey Orchestration
title: distinctCountWithNull
description: 瞭解distinctCountWithNull函式
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 23%

---


# distinctCountWithNull {#distinctCountWithNull}

計算包括空值在內的不同值數。

## 類別

彙總

## 函式語法

`distinctCountWithNull(<listAny>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 清單 | listString |
| 清單 | listBoolean |
| 清單 | listInteger |
| 清單 | listDecimal |
| 清單 | listDuration |
| 清單 | listDateTime |
| 清單 | listDateTimeOnly |

## 簽名和傳回的類型

`distinctCountwithNull(<listAny>)`

傳回整數。

## 範例

`distinctCountWithNull([10,2,10,null])`

返回3。
