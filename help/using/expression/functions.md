---
title: 函式
description: 瞭解函式
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: ac2ca77e2ba7c56217199dbd487f57cfe207f7d7
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 73%

---


# 函式 {#concept_p1r_qj5_dgb}

函式可以有不同的簽名（一組不同的有序參數）。 函式簽名可以具有0-N表達式作為有序參數。

`<function name>`(`<expression as param 1>`, `<expression as param 2>`, ... ,`<expression as param N>`)

每個函式都有特定的傳回類型。

以下是支援的函式清單。

## 主要功能

| 類別 | 函式 |
|-------------|-----------------------|
| Adobe Experience Platform | [inSegment](../functions/functioninsegment.md) |
| 彙總 | [avg](../functions/functionavg.md) |
| 彙總 | [count](../functions/functioncount.md) |
| 彙總 | [countOnlyNull](../functions/functioncountonlynull.md) |
| 彙總 | [countWithNull](../functions/functioncountwithnull.md) |
| 彙總 | [distinctCount](../functions/functiondistinctcount.md) |
| 彙總 | [distinctCountWithNull](../functions/functiondistinctcountwithnull.md) |
| 彙總 | [max](../functions/functionmax.md) |
| 彙總 | [min](../functions/functionmin.md) |
| 彙總 | [sum](../functions/functionsum.md) |
| 轉換 | [toBool](../functions/functiontobool.md) |
| 轉換 | [toDateTime](../functions/functiontodatetime.md) |
| 轉換 | [toDateTimeOnly](../functions/functiontodatetimeonly.md) |
| 轉換 | [toDecimal](../functions/functiontodecimal.md) |
| 轉換 | [toDuration](../functions/functiontoduration.md) |
| 轉換 | [toInteger](../functions/functiontointeger.md) |
| 轉換 | [toString](../functions/functiontostring.md) |
| 日期 | [currentTimeInMillis](../functions/functioncurrenttimeinmillis.md) |
| 日期 | [inLastDays](../functions/functioninlastdays.md) |
| 日期 | [inLastHours](../functions/functioninlasthours.md) |
| 日期 | [inLastMonths](../functions/functioninlastmonths.md) |
| 日期 | [inLastYears](../functions/functioninlastyears.md) |
| 日期 | [inNextDays](../functions/functioninnextdays.md) |
| 日期 | [inNextHours](../functions/functioninnexthours.md) |
| 日期 | [inNextMonths](../functions/functioninnextmonths.md) |
| 日期 | [inNextYears](../functions/functioninnextyears.md) |
| 日期 | [now](../functions/functionnow.md) |
| 日期 | [nowWithDelta](../functions/functionnowwithdelta.md) |
| 日期 | [setHours](../functions/functionsethours.md) |
| 日期 | [setDays](../functions/functionsetdays.md) |
| 清單 | [distict](../functions/functiondistinct.md) |
| 清單 | [distinctCount](../functions/functiondistinctcount.md) |
| 清單 | [in](../functions/functionin.md) |
| 清單 | [listSize](../functions/functionlistsize.md) |
| 清單 | [serializeList](../functions/functionserializelist.md) |
| 清單 | [sort](../functions/functionsort.md) |
| 數學 | [random](../functions/functionrandom.md) |
| 數學 | [round](../functions/functionround.md) |
| String | [concat](../functions/functionconcat.md) |
| String | [contain](../functions/functioncontain.md) |
| String | [containWithIgnoreCase](../functions/functioncontainwithignorecase.md) |
| String | [endWith](../functions/functionendwith.md) |
| String | [endWithIgnoreCase](../functions/functionendwithignorecase.md) |
| String | [equalWithIgnoreCase](../functions/functionequalignorecase.md) |
| String | [indexOf](../functions/functionindexof.md) |
| String | [isEmpty](../functions/functionisempty.md) |
| String | [isNotEmpty](../functions/functionisnotempty.md) |
| String | [lastIndexOf](../functions/functionlastindexof.md) |
| String | [length](../functions/functionlength.md) |
| String | [lower](../functions/functionlower.md) |
| String | [matchRegExp](../functions/functionmatchregexp.md) |
| String | [notEqualWithIgnoreCase](../functions/functionnotequalignorecase.md) |
| String | [replace](../functions/functionreplace.md) |
| String | [replaceAll](../functions/functionreplaceall.md) |
| String | [startWith](../functions/functionstartwith.md) |
| String | [startWithIgnoreCase](../functions/functionstartwithignorecase.md) |
| String | [substr](../functions/functionsubstr.md) |
| String | [trim](../functions/functiontrim.md) |
| String | [upper](../functions/functionupper.md) |
| String | [uid](../functions/functionuuid.md) |