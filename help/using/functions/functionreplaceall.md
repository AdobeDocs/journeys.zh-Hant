---
product: adobe campaign
solution: Journey Orchestration
title: replaceAll
description: 瞭解函式replaceAll
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 5%

---


# replaceAll {#replaceAll}

以基本字串中的取代字串取代所有符合目標字串的發生次數。

從字串開始到結束的取代，例如，在字串&quot;aaa&quot;中以&quot;b&quot;取代&quot;aa&quot;將產生&quot;ba&quot;，而非&quot;ab&quot;。

## 類別

String

## 函式語法

`replaceAll(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|--------------|
| base | 字串 |
| 目標 | 字串 |
| 替換 | 字串 |

## 簽名和傳回的類型

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

傳回字串。

## 範例

`replaceAll("Hello World", "l", "x")`

傳回&quot;Hexxo Worxd&quot;。
