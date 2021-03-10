---
product: adobe campaign
solution: Journey Orchestration
title: toBool
description: 瞭解Bool的函式
feature: 旅程
role: 資料工程師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 6%

---


# toBool {#toBool}

根據參數值的類型，將參數值轉換為布爾值。

* 從字串：嘗試將字串值轉換為布林值，如果字串值為&quot;true&quot;，則從&quot;true&quot;轉換為false
* 從數值：如果數值不等於0，則為true；否則為false

## 類別

轉換

## 函式語法

`toBool(<parameter>)`

## 參數

* 小數點
* 布林值
* 字串
* 整數

## 簽名和傳回的類型

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

傳回布林值。

## 範例

`toBool("true")`

`toBool(1)`

傳回true。

`toBool("this is not a boolean")`

傳回false。
