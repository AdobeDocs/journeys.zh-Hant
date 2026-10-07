---
product: adobe campaign
title: substr
description: 瞭解函式子字串
feature: Journeys
role: Developer
level: Experienced
exl-id: dda01de5-b865-4323-ac36-2e3d90d213ee
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
source-wordcount: '65'
ht-degree: 18%
---
# substr {#substr}

傳回開始索引和結束索引之間的字串運算式的子字串。 如果未定義結束索引，則它介於開始索引和結束索引之間。

## 類別

字串

## 函式語法

`substr(<parameters>)`

## 參數

| 參數 | 類型 |
|-------------|----------|
| 字串 | 字串 |
| beginindex | 整數 |
| endIndex | 整數 |

## 簽章與傳回的型別

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

傳回字串。

## 範例

`substr("Hello World",6)`

傳回「World」。

`substr("Hello World", 0, 5)`

傳回「Hello」。
