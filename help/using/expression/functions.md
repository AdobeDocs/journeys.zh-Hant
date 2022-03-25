---
product: adobe campaign
title: 函式
description: 瞭解函式
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b514d2e9-1444-46d5-a1ac-3591e62807c1
source-git-commit: f0cb883a09d553bb47491b750fabde54c92f3225
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 75%

---

# 函式 {#concept_p1r_qj5_dgb}

函式可以具有不同的簽名（一組不同的有序參數）。 函式簽名可以具有0-N表達式作為有序參數。

`<function name>`(`<expression as param 1>`。 `<expression as param 2>`,...。`<expression as param N>`)

每個函式都具有特定的返回類型。

下面是支援的函式清單。

## 主要功能

| 類別 | 函數 |
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
| 轉換 | [toDateOnly](../functions/functiontodateonly.md) |
| 轉換 | [toDateTime](../functions/functiontodatetime.md) |
| 轉換 | [toDateTimeOnly](../functions/functiontodatetimeonly.md) |
| 轉換 | [toDecimal](../functions/functiontodecimal.md) |
| 轉換 | [toDuration](../functions/functiontoduration.md) |
| 轉換 | [toInteger](../functions/functiontointeger.md) |
| 轉換 | [toString](../functions/functiontostring.md) |
| 日期 | [當前時間](../functions/functioncurrenttimeinmillis.md) |
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
| 日期 | [updateTimeZone](../functions/functionupdatetimezone.md) |
| 清單 | [distinct](../functions/functiondistinct.md) |
| 清單 | [distinctWithNull](../functions/functiondistinctwithnull.md) |
| 清單 | [篩選](../functions/functionfilter.md) |
| 清單 | [getListItem](../functions/functiongetlistitem.md) |
| 清單 | [在 ](../functions/functionin.md) |
| 清單 | [相交](../functions/functionintersect.md) |
| 清單 | [listSize](../functions/functionlistsize.md) |
| 清單 | [serializeList](../functions/functionserializelist.md) |
| 清單 | [sort](../functions/functionsort.md) |
| Math | [random](../functions/functionrandom.md) |
| 數學 | [round](../functions/functionround.md) |
| 字串 | [concat](../functions/functionconcat.md) |
| 字串 | [contain](../functions/functioncontain.md) |
| 字串 | [containIgnoreCase](../functions/functioncontainwithignorecase.md) |
| 字串 | [endWith](../functions/functionendwith.md) |
| 字串 | [endWithIgnoreCase](../functions/functionendwithignorecase.md) |
| 字串 | [equalIgnoreCase](../functions/functionequalignorecase.md) |
| 字串 | [indexOf](../functions/functionindexof.md) |
| 字串 | [isEmpty](../functions/functionisempty.md) |
| 字串 | [isNotEmpty](../functions/functionisnotempty.md) |
| 字串 | [lastIndexOf](../functions/functionlastindexof.md) |
| 字串 | [長度](../functions/functionlength.md) |
| 字串 | [lower](../functions/functionlower.md) |
| 字串 | [matchRegExp](../functions/functionmatchregexp.md) |
| 字串 | [notEqualIgnoreCase](../functions/functionnotequalignorecase.md) |
| 字串 | [replace](../functions/functionreplace.md) |
| 字串 | [replaceAll](../functions/functionreplaceall.md) |
| 字串 | [startWith](../functions/functionstartwith.md) |
| 字串 | [startWithIgnoreCase](../functions/functionstartwithignorecase.md) |
| 字串 | [substr](../functions/functionsubstr.md) |
| 字串 | [trim](../functions/functiontrim.md) |
| 字串 | [upper](../functions/functionupper.md) |
| 字串 | [uuid](../functions/functionuuid.md) |
