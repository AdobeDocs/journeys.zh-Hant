---
product: adobe campaign
title: updateTimeZone
description: 了解函式updateTimeZone
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 9%

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
