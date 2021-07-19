---
product: adobe campaign
title: toInteger
description: 了解函式toInteger
feature: 歷程
role: Data Engineer
level: Experienced
exl-id: 3fcbf4dd-3ca5-4f4b-b774-af6ac3170768
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 15%

---

# toInteger {#toInteger}

將引數值轉換為整數。

## 類別

轉換

## 函式語法

`toInteger(<parameter>)`

## 參數

| 參數 | 說明 |
|--- |--- |
| 字串 | 將字串值轉換為整數 |
| dateTime | 將日期轉換為毫秒數（epoch毫秒） |
| 小數 | 通過刪除小數部分將轉換為整數(示例：1.5變成1) |
| 布林值 | 若為true，則將布林值轉換為1，若為false，則將0 |

## 簽名和返回類型

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

傳回整數。

## 範例

`toInteger("4")`

返回4。
