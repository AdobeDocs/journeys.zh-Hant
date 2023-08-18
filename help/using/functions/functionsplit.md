---
product: adobe campaign
title: split
description: 瞭解函式分割
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 44499a09-19e2-4085-bf2f-7d9080ec382d
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 19%

---

# split {#split}

以分隔字串分割第一個引數字串（第二個引數字串，可以是規則運算式），以產生字串（代號）清單。

## 類別

字串

## 函式語法

`split(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 輸入字串 | 字串 |
| 分隔符號字串 | 字串 |

## 簽章與傳回型別

`split(<input string>, <separator string>)`

傳回listString。

## 範例

`split(["A_B_C"], "_")`

傳回 `["A","B","C"]`

具有下列值的事件欄位「event.appVersion」範例：「20.45.2.3434」

`split(@{event.appVersion}, "\\.")`

傳回 `["20", "45", "2", "3434"]`
