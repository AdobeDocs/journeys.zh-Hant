---
title: updateTimeZone
description: 瞭解函式updateTimeZone
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
