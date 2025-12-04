---
product: adobe campaign
title: endWith
description: 瞭解函式endWith
feature: Journeys
role: Developer
level: Experienced
exl-id: 6eee6057-1daf-4b9d-ae94-2b35843e3a49
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 25%

---

# endWith {#endWith}

如果第二個引數是第一個引數的尾碼，則傳回true。

## 類別

字串

## 函式語法

`endWith(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 字串 | 字串 |
| 尾碼 | 字串 |

## 簽章與傳回的型別

`endWith(<string>,<string>)`

傳回布林值。

## 範例

`endWith("Hello World", "World")`

傳回true。

`endWith("Hello World", "Hello")`

傳回false。
