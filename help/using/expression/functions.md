---
product: adobe campaign
title: 函數
description: 瞭解函式
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b514d2e9-1444-46d5-a1ac-3591e62807c1
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 57%

---

# 函數 {#concept_p1r_qj5_dgb}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_


函式可以有不同的簽章（不同的有序引數集）。 函式簽章可以有0-N個運算式做為排序引數。

`<function name>`(`<expression as param 1>`， `<expression as param 2>`， ... ，`<expression as param N>`)

每個函式都有特定的傳回型別。

以下是支援的函式清單。

## 主要函式

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
| 日期 | [updateTimeZone](../functions/functionupdatetimezone.md) |
| 清單 | [distinct](../functions/functiondistinct.md) |
| 清單 | [distinctWithNull](../functions/functiondistinctwithnull.md) |
| 清單 | [篩選器](../functions/functionfilter.md) |
| 清單 | [getListItem](../functions/functiongetlistitem.md) |
| 清單 | [in](../functions/functionin.md) |
| 清單 | [相交](../functions/functionintersect.md) |
| 清單 | [listSize](../functions/functionlistsize.md) |
| 清單 | [serializeList](../functions/functionserializelist.md) |
| 清單 | [sort](../functions/functionsort.md) |
| 數學 | [random](../functions/functionrandom.md) |
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
| 字串 | [length](../functions/functionlength.md) |
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
