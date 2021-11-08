---
product: adobe campaign
title: countWithNull
description: 了解函式countWithNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ea72dc20-8183-4661-8e08-ddb4f3727d3d
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 32%

---

# countWithNull {#countWithNull}

計算清單的所有元素，包括空值。

## 類別

彙總

## 函式語法

`countWithNull(<listAny>)`

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
| 清單 | listDateOnly |

## 簽名和返回類型

`countWithNull(<listAny>)`

傳回整數。

## 範例

`countWithNull([10,2,10,null])`

返回4。
