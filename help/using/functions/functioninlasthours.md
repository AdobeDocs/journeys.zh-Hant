---
title: inLastHours
description: 瞭解inLastHours的函式
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
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 8%

---


# inLastHours {#inLastHours}

如果指定的日期時間介於現在和現在之間——增量小時，則返回true。

## 類別

日期

## 函式語法

`inLastHours(<dateTime>,<delta>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 日期時間 | dateTime |
| δ | 整數 |

## 簽名和傳回類型

`inLastHours(<dateTime>,<integer>)`

傳回布林值。

## 範例

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4))`

傳回true。

`inLastHours(@{MyEvent.timestamp}, 4)`

傳回true。
