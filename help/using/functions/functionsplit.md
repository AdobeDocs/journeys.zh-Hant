---
product: adobe campaign
title: split
description: 瞭解函式拆分
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

用分隔符字串拆分第一個參數字串（第二個參數字串，可以是規則運算式），以生成字串清單（令牌）。

## 類別

字串

## 函式語法

`split(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 輸入字串 | 字串 |
| 分隔符 | 字串 |

## 簽名和返回的類型

`split(<input string>, <separator string>)`

返回listString。

## 範例

`split(["A_B_C"], "_")`

傳回 `["A","B","C"]`

事件欄位為&quot;event.appVersion&quot;且值為：&quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

傳回 `["20", "45", "2", "3434"]`
