---
product: adobe campaign
title: endWithIgnoreCase
description: 瞭解函式endWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3d14fe82-e287-4474-8d78-10efbf55d338
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 18%

---

# endWithIgnoreCase {#endWithIgnoreCase}

檢查第一個參數字串是否以特定字串結尾（第二個參數字串），而不考慮大小寫。

## 類別

字串

## 函式語法

`endWithIgnoreCase(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 字串 | 字串 |
| 尾碼 | 字串 |

## 簽名和返回的類型

`endWithIgnoreCase(<string>,<string>)`

返回布爾值。

## 範例

`endWithIgnoreCase("rowing is great", "AT")`

返回true。
