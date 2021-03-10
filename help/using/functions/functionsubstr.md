---
product: adobe campaign
solution: Journey Orchestration
title: substr
description: 瞭解函式子串
feature: 旅程
role: 資料工程師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 7%

---


# substr {#substr}

傳回begin索引和end索引之間字串運算式的子字串。 如果未定義結束索引，則它位於開始索引和結束索引之間。

## 類別

String

## 函式語法

`substr(<parameters>)`

## 參數

| 參數 | type |
|-------------|----------|
| 字串 | 字串 |
| beginIndex | 整數 |
| endIndex | 整數 |

## 簽名和傳回的類型

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

傳回字串。

## 範例

`substr("Hello World",6)`

傳回&quot;World&quot;。

`substr("Hello World", 0, 5)`

返回&quot;Hello&quot;。