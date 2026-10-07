---
product: adobe campaign
title: replaceAll
description: 瞭解函式replaceAll
feature: Journeys
role: Developer
level: Experienced
exl-id: d60059e5-6bf8-4a57-88a4-5323d5f0fa0b
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 10%
---
# replaceAll {#replaceAll}

以基礎字串中的取代字串取代所有符合目標字串的相符專案。

例如，取代會從字串的開頭到結尾進行，將字串「aaa」中的「aa」取代為「b」將會產生「ba」而非「ab」。

## 類別

字串

## 函式語法

`replaceAll(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|--------------|
| 基底 | 字串 |
| Target | 字串(RegExp) |
| 取代 | 字串 |

## 簽章與傳回的型別

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

傳回字串。

## 範例{#example}

`replaceAll("Hello World", "l", "x")`

傳回「Hexxo Worxd」。

由於目標引數是RegExp，因此根據您要取代的字串，您可能需要將部分字元逸出。 請參考[此頁面](../functions/functionreplace.md#example_2)中的範例。
