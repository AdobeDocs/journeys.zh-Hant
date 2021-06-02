---
product: adobe campaign
title: substr
description: 了解函式子字串
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: dda01de5-b865-4323-ac36-2e3d90d213ee
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '65'
ht-degree: 9%

---

# substr {#substr}

返回起始索引和結束索引之間的字串表達式的子字串。 如果未定義結束索引，則它介於開始索引和結束之間。

## 類別

String

## 函式語法

`substr(<parameters>)`

## 參數

| 參數 | type |
|-------------|----------|
| 字串 | 字串 |
| beginIndex | 整數 |
| endIndex | 整數 |

## 簽名和返回類型

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

傳回字串。

## 範例

`substr("Hello World",6)`

返回&quot;World&quot;。

`substr("Hello World", 0, 5)`

傳回&quot;Hello&quot;。
