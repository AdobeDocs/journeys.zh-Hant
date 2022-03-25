---
product: adobe campaign
title: distinctWithNull
description: 瞭解函式distinctWithNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 65a904c1-14ff-42b3-8f03-abb97ef47625
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 15%

---

# distinctWithNull {#distinctWithNull}

返回清單的不同值。 如果清單至少具有一個空值，則返回的清單中將包含一個空值。

## 類別

清單

## 函式語法

`distinctWithNull(<parameter>)`

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

`distinctWithNull(<listInteger>)`

返回整數清單。

`distinctWithNull(<listDecimal>)`

返回小數位清單。

`distinctWithNull(<listString>)`

返回字串清單。

`distinctWithNull(<listDateTimeOnly>)`

返回不考慮時區的日期時間清單。

`distinctWithNull(<listDateTime>)`

返回日期時間清單。

`distinctWithNull(<listDateOnly>)`

返回日期清單。

`distinctWithNull(<listBoolean>)`

返回布爾值清單。

`distinctWithNull(<listDuration>)`

返回持續時間清單。

## 範例

`distinctWithNull([10,2,10,null])`

返回 [10, 2，空]
