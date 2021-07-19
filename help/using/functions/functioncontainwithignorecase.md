---
product: adobe campaign
title: containWithIgnoreCase
description: 了解函式containWithIgnoreCase
feature: 歷程
role: Data Engineer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 24%

---

# containWithIgnoreCase {#containWithIgnoreCase}

檢查第二個引數字串是否包含在第一個引數字串中，而不考慮大小寫。

## 類別

字串

## 函式語法

`containWithIgnoreCase(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 字串 | 字串 |
| 搜尋的字串 | 字串 |

## 簽名和返回類型

`containWithIgnoreCase(<string>,<string>)`

傳回布林值。

## 範例

`containWithIgnoreCase("rowing is great', "GREAT")`

傳回true。
