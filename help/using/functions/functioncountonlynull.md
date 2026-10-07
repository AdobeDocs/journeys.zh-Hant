---
product: adobe campaign
title: countOnlyNull
description: 瞭解函式countOnlyNull
feature: Journeys
role: Developer
level: Experienced
exl-id: e6170a21-0418-4311-a43b-fd4f323cd020
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 32%
---
# countOnlyNull {#countOnlyNull}

計算清單中Null值的數量。

## 類別

彙總

## 函式語法

`countOnlyNull(<listAny>)`

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

`countOnlyNull(<listAny>)`

傳回整數。

## 範例

`countOnlyNull([10,2,10,null])`

傳回1。
