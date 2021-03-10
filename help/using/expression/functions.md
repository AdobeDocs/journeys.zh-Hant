---
product: adobe campaign
solution: Journey Orchestration
title: 函式
description: 瞭解函式
feature: 旅程
role: 資料工程師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 71%

---


# 函式 {#concept_p1r_qj5_dgb}

函式可以有不同的簽名（一組不同的有序參數）。 函式簽名可以具有0-N表達式作為有序參數。

`<function name>`(`<expression as param 1>`,  `<expression as param 2>`, ......................................................................................,`<expression as param N>`)

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
| 字串 | [contain](../functions/functioncontain.md) |
| 字串 | [containWithIgnoreCase](../functions/functioncontainwithignorecase.md) |
| 字串 | [endWith](../functions/functionendwith.md) |
| 字串 | [endWithIgnoreCase](../functions/functionendwithignorecase.md) |
| 字串 | [equalWithIgnoreCase](../functions/functionequalignorecase.md) |
| 字串 | [indexOf](../functions/functionindexof.md) |
| 字串 | [isEmpty](../functions/functionisempty.md) |
| 字串 | [isNotEmpty](../functions/functionisnotempty.md) |
| 字串 | [lastIndexOf](../functions/functionlastindexof.md) |
| 字串 | [length](../functions/functionlength.md) |
| 字串 | [lower](../functions/functionlower.md) |
| 字串 | [matchRegExp](../functions/functionmatchregexp.md) |
| 字串 | [notEqualWithIgnoreCase](../functions/functionnotequalignorecase.md) |
| 字串 | [replace](../functions/functionreplace.md) |
| 字串 | [replaceAll](../functions/functionreplaceall.md) |
| 字串 | [startWith](../functions/functionstartwith.md) |
| 字串 | [startWithIgnoreCase](../functions/functionstartwithignorecase.md) |
| 字串 | [substr](../functions/functionsubstr.md) |
| 字串 | [trim](../functions/functiontrim.md) |
| 字串 | [upper](../functions/functionupper.md) |
| 字串 | [uid](../functions/functionuuid.md) |