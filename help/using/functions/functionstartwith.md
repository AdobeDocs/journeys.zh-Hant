---
product: adobe campaign
solution: Journey Orchestration
title: startWith
description: 瞭解函式startWith
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 9%

---


# startWith {#startWith}

如果第二個參數是第一個參數的前置詞，則返回true。

## 類別

String

## 函式語法

`startWith(<parameters>)`

## 參數

| 參數 | 類型 |
|-------------|--------|
| 字串 | 字串 |
| 前置詞 | 字串 |

## 簽名和傳回的類型

`startWith(<string>,<string>)`

傳回布林值。

## 範例

`startWith("Hello World", "Hello")`

傳回true。

`startWith("Hello World", "World")`

傳回false。
