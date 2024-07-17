---
product: adobe campaign
title: distinctCount
description: 瞭解函式distinctCount
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b7844bce-1286-4d9e-b9e6-619c2d467c91
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 32%

---

# distinctCount{#distinctCount}

計算不同值的數目，忽略null值。

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
| 清單 | listDateOnly |

## 簽章與傳回的型別

`distinctCount(<listAny>)`

傳回整數。

## 範例

`distinctCount([10,2,10,null])`

傳回2。
