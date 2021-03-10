---
product: adobe campaign
solution: Journey Orchestration
title: split
description: 瞭解函式分割
feature: 旅程
role: 資料工程師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '67'
ht-degree: 7%

---


# split {#split}

使用分隔符串（第二個參數字串，可以是規則運算式）來分割第一個參數字串，以產生字串清單(Token)。

## 類別

String

## 函式語法

`split(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 輸入字串 | 字串 |
| 分隔符字串 | 字串 |

## 簽名和傳回類型

`split(<input string>, <separator string>)`

傳回listString。

## 範例

`split(["A_B_C"], "_")`

傳回`["A","B","C"]`

事件欄位為event.appVersion的範例，其值為：&quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

傳回`["20", "45", "2", "3434"]`
