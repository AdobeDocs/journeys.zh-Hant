---
product: adobe campaign
title: countWithNull
description: 瞭解函式countWithNull
feature: Journeys
role: Developer
level: Experienced
exl-id: ea72dc20-8183-4661-8e08-ddb4f3727d3d
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 32%

---

# countWithNull {#countWithNull}

計算清單的所有元素，包括null值。

## 類別

彙總

## 函式語法

`countWithNull(<listAny>)`

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

`countWithNull(<listAny>)`

傳回整數。

## 範例

`countWithNull([10,2,10,null])`

傳回4。
