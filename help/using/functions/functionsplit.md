---
product: adobe campaign
solution: Journey Orchestration
title: split
description: 瞭解函式分割
translation-type: tm+mt
source-git-commit: 135485c097f99483c2ddb3d03e0552f9ac134b44
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 4%

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
