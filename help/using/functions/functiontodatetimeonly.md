---
title: toDateTimeOnly
description: 瞭解函式toDateTime
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
source-wordcount: '47'
ht-degree: 8%

---


# toDateTimeOnly{#toDateTimeOnly}

將參數值轉換為僅限日期時間的值。

## 類別

轉換

## 函式語法

`toDateTimeOnly(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| ISO-8601格式的日期時間 | 字串 |
| 日期時間 | dateTime |

## 簽名和傳回的類型

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

不考慮時區而返回日期時間。

## 範例

`toDateTimeOnly ("2016-08-18T23:17:59.123Z")`

傳回2016-08-18T23:17:59.123。

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
