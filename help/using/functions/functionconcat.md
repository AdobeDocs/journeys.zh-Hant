---
product: adobe campaign
title: concat
description: 瞭解函式內容
feature: Journeys
role: Developer
level: Experienced
exl-id: 7a516705-2bbe-4b42-97fc-aeae11082002
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 27%

---

# concat {#concat}

串連兩個字串引數或字串清單。

## 類別

字串

## 函式語法

`concat(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 清單 | listString |
| 字串 | 字串 |

## 簽章與傳回的型別

`concat(<string>,<string>)`

`concat(<listString>)`

傳回字串。

## 範例

`concat("Hello","World")`

傳回「HelloWorld」。

`concat(["Hello"," ","World"])`

傳回「Hello World」。
