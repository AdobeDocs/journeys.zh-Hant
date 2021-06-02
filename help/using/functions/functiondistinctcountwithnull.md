---
product: adobe campaign
title: distinctCountWithNull
description: 了解函式distinctCountWithNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b8380d30-160e-45c2-b187-34eb42845923
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 27%

---

# distinctCountWithNull {#distinctCountWithNull}

計算包含空值的不同值的數量。

## 類別

彙總

## 函式語法

`distinctCountWithNull(<listAny>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 清單 | listString |
| 清單 | listBoolean |
| 清單 | listInteger |
| 清單 | listDecimal |
| 清單 | listDuration |
| 清單 | listDateTime |
| 清單 | listDateTimeOnly |

## 簽名和返回類型

`distinctCountwithNull(<listAny>)`

傳回整數。

## 範例

`distinctCountWithNull([10,2,10,null])`

返回3。
