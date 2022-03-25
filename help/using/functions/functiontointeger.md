---
product: adobe campaign
title: toInteger
description: 瞭解函式toInteger
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3fcbf4dd-3ca5-4f4b-b774-af6ac3170768
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 14%

---

# 到整數 {#toInteger}

將參數值轉換為整數。

## 類別

轉換

## 函式語法

`toInteger(<parameter>)`

## 參數

| 參數 | 說明 |
|--- |--- |
| 字串 | 將字串值轉換為整數 |
| 日期時間 | 將日期轉換為毫秒數（新紀元毫秒） |
| 小數 | 通過刪除小數部分轉換為整數(示例：1.5變為1 |
| 布林值 | 如果為true，則將布爾值轉換為1；如果為false，則將布爾值轉換為0 |

## 簽名和返回的類型

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

返回整數。

## 範例

`toInteger("4")`

返回4。
