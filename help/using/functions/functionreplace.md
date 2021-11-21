---
product: adobe campaign
title: replace
description: 了解函式取代
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: f30377c2-4d5e-4905-a972-8f4ccb272bc0
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 15%

---

# replace {#replace}

以基本字串中的取代字串取代與目標字串相符的第一個出現次數。

替換從字串的開頭到結尾，例如，將字串&quot;aaa&quot;中的&quot;aa&quot;取代為&quot;b&quot;將產生&quot;ba&quot;而非&quot;ab&quot;。

## 類別

字串

## 函式語法

`replace(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|--------------|
| 基礎 | 字串 |
| Target | 字串 |
| 更換 | 字串 |

## 簽名和返回類型

`replace(<base>,<target>,<replacement>)`

傳回字串。

## 範例

`replace("Hello World", "l", "x")`

返回&quot;Hexlo World&quot;。
