---
title: endWithIgnoreCase
description: 瞭解函式endWithIgnoreCase
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a844adc1a073aebfb7fd8a719e52f305079260b7
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 4%

---


# endWithIgnoreCase {#endWithIgnoreCase}

檢查第一個引數字串是否以特定字串（第二個引數字串）結尾，而不考慮大小寫。

## 類別

String

## 函式語法

`endWithIgnoreCase(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 字串 | 字串 |
| 尾碼 | 字串 |

## 簽名和傳回的類型

`endWithIgnoreCase(<string>,<string>)`

傳回布林值。

## 範例

`endWithIgnoreCase("rowing is great', "AT")`

傳回true。
