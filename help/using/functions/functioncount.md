---
product: adobe campaign
solution: Journey Orchestration
title: count
description: 瞭解函式計數
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 22%

---


# count {#count}

計算清單的元素，但不考慮空值。

## 類別

彙總

## 函式語法

`count(<listAny>)`

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

## 簽名和傳回類型

`count(<listAny>)`

傳回整數。

## 範例

`count([10,2,10,null])`

返回3。
