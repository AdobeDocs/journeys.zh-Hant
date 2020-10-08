---
title: inLastMonths
description: 瞭解LastMonths中的函式
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
source-wordcount: '44'
ht-degree: 9%

---


# inLastMonths {#inLastMonths}

如果指定的date或dateTime介於現在和現在- delta月份，則傳回true。

## 類別

日期

## 函式語法

`inLastMonths(<dateTime>,<delta>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 日期時間 | dateTime |
| δ | 整數 |

## 簽名和傳回類型

`inLastMonths(<dateTime>,<integer>)`

傳回布林值。

## 範例

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4))`

傳回true。
