---
product: adobe campaign
title: replaceAll
description: 瞭解函式replaceAll
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d60059e5-6bf8-4a57-88a4-5323d5f0fa0b
source-git-commit: 8980df5cc238a7195f01a1631e418a8de677fbea
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 10%

---

# 全部替換 {#replaceAll}

用基本字串中的替換字串替換與目標字串匹配的所有匹配項。

替換從字串的開頭到結尾，例如，在字串&quot;aaa&quot;中將&quot;aa&quot;替換為&quot;b&quot;將導致&quot;ba&quot;而不是&quot;ab&quot;。

## 類別

字串

## 函式語法

`replaceAll(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|--------------|
| 基礎 | 字串 |
| Target | 字串(RegExp) |
| 替換 | 字串 |

## 簽名和返回的類型

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

返回字串。

## 範例{#example}

`replaceAll("Hello World", "l", "x")`

返回&quot;Hexxo Worxd&quot;。

由於目標參數是RegExp，因此您可能需要轉義一些字元，具體取決於要替換的字串。 請參閱中的示例 [此頁](../functions/functionreplace.md#example_2)。
