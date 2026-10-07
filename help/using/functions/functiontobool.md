---
product: adobe campaign
title: toBool
description: 瞭解函式toBool
feature: Journeys
role: Developer
level: Experienced
exl-id: 490144c2-1ecd-4772-ab15-e23b1b7d8f0c
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
source-wordcount: '75'
ht-degree: 12%
---
# toBool {#toBool}

根據其型別，將引數值轉換為布林值。

* 從字串：嘗試將字串值轉換為布林值，如果字串值為「true」，則從「true」，否則為false
* 從數值：如果數值不等於0，則為true；否則為false

## 類別

轉換

## 函式語法

`toBool(<parameter>)`

## 參數

* 小數
* 布林值
* 字串
* 整數

## 簽章與傳回的型別

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

傳回布林值。

## 範例

`toBool("true")`

`toBool(1)`

傳回true。

`toBool("this is not a boolean")`

傳回false。
