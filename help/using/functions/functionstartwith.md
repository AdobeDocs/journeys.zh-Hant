---
product: adobe campaign
title: startWith
description: 瞭解函式startWith
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: bf0e75d6-cc7c-4a76-b215-8735eb62163b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 25%

---

# startWith {#startWith}

如果第二個引數是第一個引數的前置詞，則傳回true。

## 類別

字串

## 函式語法

`startWith(<parameters>)`

## 參數

| 參數 | 類型 |
|-------------|--------|
| 字串 | 字串 |
| 前置詞 | 字串 |

## 簽章與傳回的型別

`startWith(<string>,<string>)`

傳回布林值。

## 範例

`startWith("Hello World", "Hello")`

傳回true。

`startWith("Hello World", "World")`

傳回false。
