---
title: replace
description: 瞭解函式取代
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 5%

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
