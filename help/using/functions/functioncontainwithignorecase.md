---
product: adobe campaign
solution: Journey Orchestration
title: containWithIgnoreCase
description: 瞭解包含WithIgnoreCase的函式
feature: 旅程
role: 資料工程師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 9%

---


# containWithIgnoreCase {#containWithIgnoreCase}

檢查第二個引數字串是否包含在第一個引數字串中，而不考慮大小寫。

## 類別

String

## 函式語法

`containWithIgnoreCase(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 字串 | 字串 |
| 字串搜尋 | 字串 |

## 簽名和傳回的類型

`containWithIgnoreCase(<string>,<string>)`

傳回布林值。

## 範例

`containWithIgnoreCase("rowing is great', "GREAT")`

傳回true。
