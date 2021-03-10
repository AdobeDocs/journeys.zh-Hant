---
product: adobe campaign
solution: Journey Orchestration
title: concat
description: 瞭解函式概念
feature: 旅程
role: 資料工程師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 13%

---


# concat {#concat}

串連兩個字串參數或字串清單。

## 類別

String

## 函式語法

`concat(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 清單 | listString |
| 字串 | 字串 |

## 簽名和傳回的類型

`concat(<string>,<string>)`

`concat(<listString>)`

傳回字串。

## 範例

`concat("Hello","World")`

傳回&quot;HelloWorld&quot;。

`concat(["Hello"," ","World"])`

返回&quot;Hello World&quot;。
