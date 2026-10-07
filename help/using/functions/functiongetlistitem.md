---
product: adobe campaign
title: getListItem
description: 瞭解函式gstListItem
feature: Journeys
role: Developer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
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
source-wordcount: '93'
ht-degree: 19%
---
# getListItem {#gestListItem}

傳回指定索引處的清單專案。

## 類別

清單

## 函式語法

`getListItem(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| list | listString |
| list | listBoolean |
| list | listInteger |
| list | listDecimal |
| list | listDuration |
| list | listDateTime |
| list | listDateTimeOnly |
| list | listDateOnly |
| 索引 | 整數 |

## 簽章與傳回型別

`getListItem(<listInteger>,<index>)`

傳回整數。

`getListItem(<listDecimal>,<index>)`

傳回小數。

`getListItem(<listString>,<index>)`

傳回字串。

`getListItem(<listDateTimeOnly>,<index>)`

傳回日期時間，不考慮時區。

`getListItem(<listDateTime>,<index>)`

傳回日期時間。

`getListItem(<listDateOnly>,<index>)`

傳回日期清單。

`getListItem(<listBoolean>,<index>)`

傳回布林值。

`getListItem(<listDuration>,<index>)`

傳回持續時間。

## 範例

`getListItem([10, 2, 3], 1)`

傳回「2」

`getListItem(["A", "B", "C"], 2)`
傳回「C」

具有事件欄位「event.appVersion」且值為「20.45.2.3434」的範例

`split(@{event.appVersion}, "\\.")`

傳回`["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

傳回「20」
