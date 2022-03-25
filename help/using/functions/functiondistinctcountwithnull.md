---
product: adobe campaign
title: distinctCountWithNull
description: 瞭解函式distinctCountWithNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b8380d30-160e-45c2-b187-34eb42845923
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 32%

---

# distinctCountWithNull {#distinctCountWithNull}

計算包括空值在內的不同值的數量。

## 類別

彙總

## 函式語法

`distinctCountWithNull(<listAny>)`

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

`distinctCountWithNull(<listAny>)`

返回整數。

## 範例

`distinctCountWithNull([10,2,10,null])`

返回3。
