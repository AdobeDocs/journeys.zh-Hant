---
product: adobe campaign
title: updateTimeZone
description: 了解函式updateTimeZone
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: a5d063784b278120b61f8d2641264baf40e34a90
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 7%

---

# updateTimeZone {#updateTimeZone}

傳回新日期時間，並在同一時間內傳回新時區。

## 類別

Date

## 函式語法

`updateTimeZone(<parameters>)`

## 參數

* 時區id:字串
* dateTime

## 簽名和返回類型

`updateTimeZone(<dateTime>,<timeZone id>)`

返回日期時間。

## 範例

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

傳回2019-08-28T17:15:30.123+02:00。

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`
Returns "2019-08-28T17:15:30.123+02:00".-->

`updateTimeZone(@{MyExpEvent.timestamp}, "Australia/Sydney")`

如果時間戳記欄位的值為 `2021-11-16T16:55:12.939318+01:00`，則函式會傳回 `2021-11-17T02:55:12.942115+11:00`.
