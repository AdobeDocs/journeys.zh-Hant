---
product: adobe campaign
title: toDateOnly
description: 瞭解函式toDateOnly
feature: Journeys
role: Developer
level: Experienced
exl-id: 2d7b132e-5ee0-4fa0-bacc-ce4c6ec7e794
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 16%

---

# toDateOnly{#toDateOnly}

將引數值轉換為僅日期值。

## 類別

轉換

## 函式語法

`toDateOnly(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| ISO-8601或&quot;YYYY-MM-DD&quot;格式的日期（XDM日期格式） | 字串 |
| 日期 | 日期 |

## 簽章與傳回的型別

`toDateOnly(<date>)`

`toDateOnly(<string>)`

傳回日期時間而不考慮時區。

## 範例

`toDateOnly("2016-08-18")`

傳回代表2016-08-18的dateOnly物件。
