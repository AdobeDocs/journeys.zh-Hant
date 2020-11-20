---
product: adobe campaign
solution: Journey Orchestration
title: concat
description: 瞭解函式概念
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 12%

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
