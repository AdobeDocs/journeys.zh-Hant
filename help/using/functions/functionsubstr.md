---
title: substr
description: 瞭解函式子串
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# substr {#substr}

傳回begin索引和end索引之間字串運算式的子字串。 如果未定義結束索引，則它位於開始索引和結束索引之間。

## 類別

字串

## 函式語法

`substr(<parameters>)`

## 參數

| 參數 | type |
|-------------|----------|
| 字串 | 字串 |
| beginIndex | 整數 |
| endIndex | 整數 |

## 簽名和傳回的類型

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

傳回字串。

## 範例

`substr("Hello World",6)`

傳回&quot;World&quot;。

`substr("Hello World", 0, 5)`

返回&quot;Hello&quot;。