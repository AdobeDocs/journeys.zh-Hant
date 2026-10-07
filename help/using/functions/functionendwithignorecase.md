---
product: adobe campaign
title: endWithIgnoreCase
description: 瞭解函式endWithIgnoreCase
feature: Journeys
role: Developer
level: Experienced
exl-id: 3d14fe82-e287-4474-8d78-10efbf55d338
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
source-wordcount: '48'
ht-degree: 18%
---
# endWithIgnoreCase {#endWithIgnoreCase}

檢查第一個引數字串是否以特定字串（第二個引數字串）結尾，並未考慮大小寫。

## 類別

字串

## 函式語法

`endWithIgnoreCase(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 字串 | 字串 |
| 尾碼 | 字串 |

## 簽章與傳回的型別

`endWithIgnoreCase(<string>,<string>)`

傳回布林值。

## 範例

`endWithIgnoreCase("rowing is great", "AT")`

傳回true。
