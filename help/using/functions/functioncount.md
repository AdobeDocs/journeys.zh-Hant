---
product: adobe campaign
title: 計數
description: 瞭解函式計數
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 46528642-18d5-4ca9-a344-de2c7f939d00
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 30%

---

# 計數 {#count}

計算清單的元素而不考慮null值。

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
| 清單 | listDateOnly |

## 簽章與傳回型別

`count(<listAny>)`

傳回整數。

## 範例

`count([10,2,10,null])`

傳回3。
