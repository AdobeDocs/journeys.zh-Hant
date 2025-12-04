---
product: adobe campaign
title: endWithIgnoreCase
description: 瞭解函式endWithIgnoreCase
feature: Journeys
role: Developer
level: Experienced
exl-id: 3d14fe82-e287-4474-8d78-10efbf55d338
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
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
