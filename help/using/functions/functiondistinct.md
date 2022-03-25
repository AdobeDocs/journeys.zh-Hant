---
product: adobe campaign
title: distinct
description: 瞭解不同的功能
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 034e4d77-2f0e-4117-9fd4-b9e35ef71a39
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 18%

---

# 獨特 {#distinct}

返回清單中不帶空值的不同值。

## 類別

清單

## 函式語法

`distinct(<parameter>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 清單 | 清單字串 |
| 清單 | list布爾 |
| 清單 | listInteger |
| 清單 | 清單十進位 |
| 清單 | listDuration（持續時間） |
| 清單 | 清單日期時間 |
| 清單 | listDateTimeOnly |
| 清單 | listDateOnly |

## 簽名和返回的類型

`distinct(<listInteger>)`

返回整數清單。

`distinct(<listDecimal>)`

返回小數位清單。

`distinct(<listString>)`

返回字串清單。

`distinct(<listDateTimeOnly>)`

返回不考慮時區的日期時間清單。

`distinct(<listDateTime>)`

返回日期時間清單。

`distinct(<listDateOnly>)`

返回日期清單。

`distinct(<listBoolean>)`

返回布爾值清單。

`distinct(<listDuration>)`

返回持續時間清單。

## 範例

`distinct([10,2,10,null])`

傳回 `[10, 2]`.
