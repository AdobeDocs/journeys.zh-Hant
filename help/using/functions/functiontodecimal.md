---
product: adobe campaign
solution: Journey Orchestration
title: toDecimal
description: 瞭解Decimal函式
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 7%

---


# toDecimal {#toDecimal}

根據參數值的類型將參數值轉換為小數值。

## 類別

轉換

## 函式語法

`toDecimal(<parameter>)`

## 參數

| 參數 | 說明 |
|--- |--- |
| 字串 | 將字串值轉換為小數 |
| dateTime | 將日期轉換為毫秒數（紀元毫秒） |
| 布林值 | 將布林值轉換為1（如果為true）,0（如果為false） |
| 整數 | 轉換為小數（示例）。:1變為1.0) |

## 簽名和傳回的類型

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

傳回小數。

## 範例

`toDecimal("4.0")`

返回4.0。
