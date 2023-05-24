---
product: adobe campaign
title: getListItem
description: 瞭解gstListItem函式
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 21%

---

# getListItem {#gestListItem}

返回給定索引處的清單項。

## 類別

清單

## 函式語法

`getListItem(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| list | 清單字串 |
| list | list布爾 |
| list | listInteger |
| list | 清單十進位 |
| list | listDuration（持續時間） |
| list | 清單日期時間 |
| list | listDateTimeOnly |
| list | listDateOnly |
| 索引 | 整數 |

## 簽名和返回的類型

`getListItem(<listInteger>,<index>)`

返回整數。

`getListItem(<listDecimal>,<index>)`

返回十進位。

`getListItem(<listString>,<index>)`

返回字串。

`getListItem(<listDateTimeOnly>,<index>)`

返回不考慮時區的日期時間。

`getListItem(<listDateTime>,<index>)`

返回日期時間。

`getListItem(<listDateOnly>,<index>)`

返回日期清單。

`getListItem(<listBoolean>,<index>)`

返回布爾值。

`getListItem(<listDuration>,<index>)`

返回持續時間。

## 範例

`getListItem([10, 2, 3], 1)`

返回&quot;2&quot;

`getListItem(["A", "B", "C"], 2)`
返回&quot;C&quot;

事件欄位「event.appVersion」的示例，其值為：&quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

傳回 `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

返回&quot;20&quot;
