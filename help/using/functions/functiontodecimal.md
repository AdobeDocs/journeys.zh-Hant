---
product: adobe campaign
title: toDecimal
description: 瞭解函式toDecimal
feature: Journeys
role: Developer
level: Experienced
exl-id: 11d7013c-2190-4654-8466-920861c836f5
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
source-wordcount: '76'
ht-degree: 14%
---
# toDecimal {#toDecimal}

根據其型別，將引數值轉換為十進位值。

## 類別

轉換

## 函式語法

`toDecimal(<parameter>)`

## 參數

| 參數 | 說明 |
|--- |--- |
| 字串 | 將字串值轉換為小數 |
| dateTime | 將日期轉換為毫秒數（紀元毫秒） |
| 布林值 | 如果為true，則將布林值轉換為1，如果為false，則轉換為0 |
| 整數 | 轉換為小數（範例： 1變成1.0） |

## 簽章與傳回的型別

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

傳回小數。

## 範例

`toDecimal("4.0")`

傳回4.0。
