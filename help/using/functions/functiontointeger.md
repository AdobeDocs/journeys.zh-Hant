---
product: adobe campaign
solution: Journey Orchestration
title: toInteger
description: 瞭解函式toInteger
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 7%

---


# toInteger {#toInteger}

將參數值轉換為整數。

## 類別

轉換

## 函式語法

`toInteger(<parameter>)`

## 參數

| 參數 | 說明 |
|--- |--- |
| 字串 | 將字串值轉換為整數 |
| dateTime | 將日期轉換為毫秒數（紀元毫秒） |
| 小數點 | 通過刪除小數部分轉換為整數(例如：1.5變為1) |
| 布林值 | 將布林值轉換為1（如果為true）,0（如果為false） |

## 簽名和傳回類型

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

傳回整數。

## 範例

`toInteger(4)`

返回4。
