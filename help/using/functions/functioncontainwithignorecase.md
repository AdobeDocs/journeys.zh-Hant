---
product: adobe campaign
solution: Journey Orchestration
title: containWithIgnoreCase
description: 瞭解包含WithIgnoreCase的函式
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 8%

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
