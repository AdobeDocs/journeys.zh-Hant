---
title: containWithIgnoreCase
description: 瞭解包含WithIgnoreCase的函式
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
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
