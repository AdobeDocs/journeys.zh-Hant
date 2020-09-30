---
title: toDateTime
description: 瞭解函式toDateTime
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 70bc6653a8cdd552a0441f4b661341d3f095b112
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# toDateTime {#toDateTime}

根據參數的類型，將參數轉換為日期時間值。

## 類別

轉換

## 函式語法

`toDateTime(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| ISO-8601格式的日期時間 | 字串 |
| 時區ID | 字串 |
| 無時區的日期時間 | dateTimeOnly |
| 一個紀元的整數值（以毫秒為單位） | 整數 |

>[!NOTE]
>
>時區ID必須是字串常數。 它不能是欄位引用或表達式。 有關資料類型的詳細資訊，請參閱 [](../expression/data-types.md)。

## 簽名和傳回的類型

`toDateTime(<string>)`

`toDateTime(<dateTimeOnly>,<stringified time zone id>)`

`toDateTime(<integer>)`

傳回 **dateTime**。

<!--`toDateTime(<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`

Returns a date time with default time zone UTC.

`toDateTime(<year>,<month>,<dayOfMonth>)`
`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>)`
`toDateTime(<timeZone>,<year>,<month>,<dayOfMonth>)`

Return a datetime where hour, minute and second set to 0.

`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`
`toDateTime(<string>)`
`toDateTime(<string>,<integer>)`
`toDateTime(<stringified timeZone>,<dateTimeOnly)`

`toDateTime(<timeZone>,<integer>)`

Return a datetime.

-->

## 範例

`toDateTime ("2016-08-18T23:17:59.123Z")`

傳回2016-08-18T23:17:59.123Z

`toDateTime(toDateTimeOnly("2016-08-18T23:17:59.123"),"UTC")`

傳回2016-08-18T23:17:59.123Z

`toDateTime(1560762190189)`

傳回2019-06-17T09:03:10.189Z

<!--`toDateTime ("2016-08-18T23:17:59.123", "UTC")`

Returns 2016-08-18T23:17:59.123Z.

`toDateTime("Z",2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000Z.

`toDateTime("Z",2016,8,18)`

Returns 2016-08-18T00:00:00.000Z.-->
