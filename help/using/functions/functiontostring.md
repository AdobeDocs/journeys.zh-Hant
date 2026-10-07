---
product: adobe campaign
title: toString
description: 瞭解函式toString
feature: Journeys
role: Developer
level: Experienced
exl-id: 942e7a44-1cb1-4c99-abd6-e0b045c42c80
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
source-wordcount: '107'
ht-degree: 9%
---
# toString {#toString}

根據其型別，將引數值轉換為字串值。 如需資料型別的詳細資訊，請參閱[此頁面](../expression/data-types.md)。

## 類別

轉換

## 函式語法

`toString(<parameter>)`

## 參數

| 參數 | 說明 |
|--- |--- |
| dateTime | 將日期轉換為UTC日期格式 |
| dateTimeOnly | 將日期轉換為UTC日期格式 |
| 期間 | 轉換為字串形式的對應毫秒數 |
| 整數 | 轉換為值的字串表示法（1會變成「1」） |
| 小數 | 轉換為值的字串表示法（1.5會變成&quot;1.5&quot;） |
| 布林值 | 將布林值轉換為&#39;true&#39; （如果為true），&#39;false&#39; （如果為false） |

## 簽章與傳回型別

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

傳回字串。

## 範例

`toString(4)`

傳回「4」。
