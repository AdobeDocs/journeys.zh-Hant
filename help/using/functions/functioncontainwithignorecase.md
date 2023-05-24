---
product: adobe campaign
title: containIgnoreCase
description: 瞭解包含IgnoreCase的函式
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 22%

---

# containIgnoreCase {#containIgnoreCase}

檢查第二個參數字串是否包含在第一個參數字串中，而不考慮大小寫。

## 類別

字串

## 函式語法

`containIgnoreCase(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 字串 | 字串 |
| 字串搜索 | 字串 |

## 簽名和返回的類型

`containIgnoreCase(<string>,<string>)`

返回布爾值。

## 範例

`containIgnoreCase("rowing is great", "GREAT")`

返回true。
