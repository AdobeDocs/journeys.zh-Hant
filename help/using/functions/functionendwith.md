---
product: adobe campaign
solution: Journey Orchestration
title: endWith
description: 瞭解函式endWith
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 9%

---


# endWith {#endWith}

如果第二個參數是第一個參數的尾碼，則返回true。

## 類別

String

## 函式語法

`endWith(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 字串 | 字串 |
| 尾碼 | 字串 |

## 簽名和傳回的類型

`endWith(<string>,<string>)`

傳回布林值。

## 範例

`endWith("Hello World", "World")`

傳回true。

`endWith("Hello World", "Hello")`

傳回false。
