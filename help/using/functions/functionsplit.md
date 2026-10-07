---
product: adobe campaign
title: split
description: 瞭解函式分割
feature: Journeys
role: Developer
level: Experienced
exl-id: 44499a09-19e2-4085-bf2f-7d9080ec382d
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
source-wordcount: '64'
ht-degree: 15%
---
# split {#split}

以分隔字串分割第一個引數字串（第二個引數字串，可以是規則運算式），以產生字串（代號）清單。

## 類別

字串

## 函式語法

`split(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 輸入字串 | 字串 |
| 分隔符號字串 | 字串 |

## 簽章與傳回型別

`split(<input string>, <separator string>)`

傳回listString。

## 範例

`split(["A_B_C"], "_")`

傳回`["A","B","C"]`

具有下列值的事件欄位「event.appVersion」範例：「20.45.2.3434」

`split(@{event.appVersion}, "\\.")`

傳回`["20", "45", "2", "3434"]`
