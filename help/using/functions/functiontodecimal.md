---
product: adobe campaign
title: toDecimal
description: 瞭解函式toDecimal
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 11d7013c-2190-4654-8466-920861c836f5
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
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
| 整數 | 轉換為小數（範例）。：1變為1.0) |

## 簽章與傳回的型別

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

傳回小數。

## 範例

`toDecimal("4.0")`

傳回4.0。
