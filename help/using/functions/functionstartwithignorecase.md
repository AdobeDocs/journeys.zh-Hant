---
product: adobe campaign
solution: Journey Orchestration
title: startWithIgnoreCase
description: 瞭解函式startWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

---


# startWithIgnoreCase {#startWithIgnoreCase}

如果第二個參數是第一個參數的前置詞而不考慮大小寫，則返回true。

## 類別

String

## 函式語法

`startWithIgnoreCase(<parameters>)`

## 參數

| 參數 | 類型 |
|-------------|--------|
| 字串 | 字串 |
| 前置詞 | 字串 |

## 簽名和傳回的類型

`startWithIgnoreCase(<string>,<string>)`

傳回布林值。

## 範例

`startWith("rowing is great', "RO")`

傳回true。
