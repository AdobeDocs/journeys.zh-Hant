---
product: adobe campaign
title: toDateOnly
description: 了解函式toDateOnly
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 5e2af021f1c82063fcc0d4e4b5edf13c57cc6c72
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 17%

---

# toDateOnly{#toDateOnly}

將引數值轉換為僅限日期的值。

## 類別

轉換

## 函式語法

`toDateOnly(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 日期格式（XDM日期格式） | 字串 |
| 日期 | 日期 |

## 簽名和返回的類型

`toDateOnly(<date>)`

`toDateOnly(<string>)`

不考慮時區而返回日期時間。

## 範例

`toDateOnly("2016-08-18")`

傳回代表2016-08-18的dateOnly物件。