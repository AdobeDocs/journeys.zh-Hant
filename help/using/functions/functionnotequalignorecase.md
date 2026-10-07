---
product: adobe campaign
title: notEqualIgnoreCase
description: 瞭解函式notEqualIgnoreCase
feature: Journeys
role: Developer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
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
source-wordcount: '37'
ht-degree: 13%
---
# notEqualIgnoreCase {#notEqualIgnoreCase}

檢查第一個引數字串是否與第二個引數字串不同，忽略大小寫考量。

## 類別

字串

## 函式語法

`notEqualIgnoreCase(<parameters>)`

## 參數

* 字串

## 簽章與傳回的型別

`notEqualIgnoreCase(<string>,<string>)`

傳回布林值。

## 範例

`notEqualIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad")`
