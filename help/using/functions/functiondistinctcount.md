---
product: adobe campaign
title: distinctCount
description: 了解函式distinctCount
feature: 歷程
role: Data Engineer
level: Experienced
exl-id: b7844bce-1286-4d9e-b9e6-619c2d467c91
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 33%

---

# distinctCount{#distinctCount}

計算忽略空值的不同值的數量。

## 類別

彙總

## 函式語法

`distinctCount(<listAny>)`

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

## 簽名和返回類型

`distinctCount(<listAny>)`

傳回整數。

## 範例

`distinctCount([10,2,10,null])`

傳回2。
