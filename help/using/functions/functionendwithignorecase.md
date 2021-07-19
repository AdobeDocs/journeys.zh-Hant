---
product: adobe campaign
title: endWithIgnoreCase
description: 了解函式endWithIgnoreCase
feature: 歷程
role: Data Engineer
level: Experienced
exl-id: 3d14fe82-e287-4474-8d78-10efbf55d338
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 20%

---

# endWithIgnoreCase {#endWithIgnoreCase}

檢查第一個引數字串結尾是否為特定字串（第二個引數字串），不考慮大小寫。

## 類別

字串

## 函式語法

`endWithIgnoreCase(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 字串 | 字串 |
| 尾碼 | 字串 |

## 簽名和返回類型

`endWithIgnoreCase(<string>,<string>)`

傳回布林值。

## 範例

`endWithIgnoreCase("rowing is great', "AT")`

傳回true。
