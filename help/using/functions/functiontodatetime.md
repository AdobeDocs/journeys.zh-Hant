---
product: adobe campaign
title: toDateTime
description: 了解函式toDateTime
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 0b8d1a82-a55a-4a4d-ad1b-35499d52b469
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 6%

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
| 時區id | 字串 |
| 無時區的日期時間 | dateTimeOnly |
| 以毫秒為單位的整數值 | 整數 |

>[!NOTE]
>
>時區ID必須是字串常數。 它不能是欄位參考或運算式。 有關資料類型的詳細資訊，請參閱[本頁](../expression/data-types.md)。

## 簽名和返回的類型

`toDateTime(<string>)`

`toDateTime(<dateTimeOnly>,<stringified time zone id>)`

`toDateTime(<integer>)`

傳回&#x200B;**dateTime**。

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

返回2016-08-18T23:17:59.123Z

`toDateTime(toDateTimeOnly("2016-08-18T23:17:59.123"),"UTC")`

返回2016-08-18T23:17:59.123Z

`toDateTime(1560762190189)`

傳回2019-06-17T09:03:10.189Z

<!--`toDateTime ("2016-08-18T23:17:59.123", "UTC")`

Returns 2016-08-18T23:17:59.123Z.

`toDateTime("Z",2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000Z.

`toDateTime("Z",2016,8,18)`

Returns 2016-08-18T00:00:00.000Z.-->
