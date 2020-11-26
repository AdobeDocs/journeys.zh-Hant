---
product: adobe campaign
solution: Journey Orchestration
title: 資料類型
description: 瞭解進階運算式中的資料類型
translation-type: tm+mt
source-git-commit: 062b4648e2eb3a4270f9c09e4478d541209e1247
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 4%

---


# 資料類型 {#concept_gp3_rj5_dgb}

從技術上講，常數一律包含資料類型。 在常值運算式中，我們只指定值。 您可從值（例如字串、整數、小數等）推斷資料類型。 對於特定情況（例如日期時間），我們使用專屬函式來表示。

以下各節提供不同資料類型運算式的相關資訊，以及其表示方式。

## string {#string}

**說明**

常見的字元順序。 除了來自環境（如可用記憶體量）的隱式大小外，它沒有任何特定大小。

JSON格式：字串

序列化格式：UTF-8

**常值表示法**

```
"<value>"
```

```
'<value>'
```

**範例**

```
"hello world"
```

```
'hello world'
```

## 整數 {#integer}

**說明**

從-2^63到2^63-1的整數值。

JSON格式：數字

**常值表示法**

```
<integer value>
```

**範例**

```
42
```

## 小數點 {#decimal}

**說明**

小數。 它代表浮動值：

* (2-2^-52)x2^1023型雙的最大正有限值
* 雙型，2-1022的最小正常值
* 雙型最小正非零值，2 p-1074

JSON格式：數字

序列化格式：使用&#39;.&#39; 作為小數分隔符。

**常值表示法**

```
<integer value>.<integer value>
```

**範例**

```
3.14
```

## 布林值 {#boolean}

**說明**

寫成小寫的布爾值：true或false

JSON格式：布林值

**常值表示法**

```
true
```

```
false
```

**範例**

```
true
```

## dateTimeOnly {#date-time-only}

**說明**

表示沒有時區的日期時間，視為年月日每小時每分鐘毫秒。

它不儲存或表示時區。 相反，它是日期的描述，如生日所用，加上牆鐘上的當地時間。

如果沒有額外的資訊（例如偏移或時區），則無法在時線上顯示即時。

序列化格式：ISO-8601延伸偏移日期——時間格式。

它使用DateTimeFormatter ISO_LOCAL_DATE_TIME來反序列化值。 [進一步瞭解](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**常值表示法**

```
toDateTimeOnly("<dateTimeOnly in ISO-8601 format>")  
```

## dateTime {#date-time}

**說明**

也會考慮時區的日期時間常數。 它表示與UTC偏移的日期時間。

它可與偏移的額外資訊即時檢視。 這是在世界某個地方代表一個特定「時刻」的一種方式。

JSON格式：字串。

它必須封裝在toDateTime函式中。

序列化格式：ISO-8601延伸偏移日期——時間格式。

它使用DateTimeFormatter ISO_OFFSET_DATE_TIME來反序列化值。 [進一步瞭解](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

您也可以傳遞一個傳遞紀元值的整數。 [顯示全文](https://www.epochconverter.com)

時區可由偏移或時區代碼指定(例如：歐洲／巴黎， Z —— 意為UTC)。

**常值表示法**

```
toDateTime("<dateTime in ISO-8601 format>")
```

```
toDateTime(<integer value of an epoch in milliseconds>)
```

**範例**

```
toDateTime("1977-04-22T06:00:00Z")
```

```
toDateTime("2011-12-03T15:15:30Z")
```

```
toDateTime("2011-12-03T15:15:30.123Z")
```

```
toDateTime("2011-12-03T15:15:30.123+02:00")
```

```
toDateTime("2011-12-03T15:15:30.123-00:20")
```

```
toDateTime(1560762190189)
```

## 持續時間 {#duration}

**說明**

它代表以時間為基礎的時間量，例如&#39;34.5秒&#39;。 它以毫秒為單位來模擬量或時間量。

支援的臨時單元包括：毫秒、秒、分鐘、小時、日等於24小時的天數。 年份和月份不受支援，因為它們不是固定的時間。

JSON格式：字串。

它必須封裝在toDuration函式中。

序列化格式：若要反序列化時區ID，它會使用java函式java.time。

Duration.parse:接受的格式基於ISO-8601持續時間格式PnDTnHnMn.nS，其天數被認為恰好為24小時。 [進一步瞭解](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**常值表示法**

```
toDuration("<duration in ISO-8601 format>")
```

```
toDuration(<duration in milliseconds>)
```

**範例**

```
toDuration("PT5S") -- parses as 5 seconds
```

```
toDuration(500) -- parses as 500ms
```

```
toDuration("PT20.345S") -- parses as "20.345 seconds"
```

```
toDuration("PT15M") -- parses as "15 minutes" (where a minute is 60 seconds)
```

```
toDuration("PT10H")  -- parses as "10 hours" (where an hour is 3600 seconds)
```

```
toDuration("P2D") -- parses as "2 days" (where a day is 24 hours or 86400 seconds)
```

```
toDuration("P2DT3H4M") -- parses as "2 days, 3 hours and 4 minutes"
```

```
toDuration("P-6H3M") -- parses as "-6 hours and +3 minutes"
```

```
toDuration("-P6H3M") -- parses as "-6 hours and -3 minutes"
```

```
toDuration("-P-6H+3M") -- parses as "+6 hours and -3 minutes"
```

## list {#list}

**說明**

使用方括弧作為分隔字元的運算式清單（以逗號分隔）。

不支援多態性，因此清單中包含的所有表達式都應具有相同的類型。

**常值表示法**

```
[<expression>, <expression>, ... ]
```

**範例**

```
["value1","value2"]
```

```
[3,5]
```

```
[toDuration(500),toDuration(800)]
```
