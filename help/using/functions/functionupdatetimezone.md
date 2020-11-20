---
product: adobe campaign
solution: Journey Orchestration
title: updateTimeZone
description: 瞭解函式updateTimeZone
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 4%

---


# updateTimeZone {#updateTimeZone}

傳回新的日期時間，同時傳回新的時區。

## 類別

日期

## 函式語法

`updateTimeZone(<parameters>)`

## 參數

* 時區ID:字串
* dateTime

## 簽名和傳回的類型

`updateTimeZone(<dateTime>,<timeZone id>)`

返回日期時間。

## 範例

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

傳回2019-08-28T17:15:30.123+02:00。

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`

Returns "2019-08-28T17:15:30.123+02:00".-->
