---
product: adobe campaign
solution: Journey Orchestration
title: replace
description: 瞭解函式取代
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 6%

---


# replace {#replace}

用基本字串中的取代字串取代第一個符合目標字串的出現點。

從字串開始到結束的取代，例如，在字串&quot;aaa&quot;中以&quot;b&quot;取代&quot;aa&quot;將產生&quot;ba&quot;，而非&quot;ab&quot;。

## 類別

String

## 函式語法

`replace(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|--------------|
| base | 字串 |
| 目標 | 字串 |
| 替換 | 字串 |

## 簽名和傳回的類型

`replace(<base>,<target>,<replacement>)`

傳回字串。

## 範例

`replace("Hello World", "l", "x")`

傳回&quot;Hexlo World&quot;。
