---
product: adobe campaign
title: 資料類型
description: 瞭解高級表達式中的資料類型
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 343f61b8-2315-4971-8b2b-6aa815bd9ced
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 5%

---

# 資料類型 {#concept_gp3_rj5_dgb}

從技術上講，常數始終包含資料類型。 在文本表達式中，我們只指定值。 資料類型可以從值（例如字串、整數、小數等）推斷。 對於特定情況（如日期時間），我們使用專用函式來表示。

以下各節提供了有關不同資料類型表達式及其表示方式的資訊。

## 字串 {#string}

**說明**

字元的常用序列。 除了來自環境的隱式大小（如可用記憶體量）外，它沒有任何特定大小。

JSON格式：字串

序列化格式：UTF-8

**文字表示**

```json
"<value>"
```

```json
'<value>'
```

**範例**

```json
"hello world"
```

```json
'hello world'
```

## 整數 {#integer}

**說明**

從–2^63到2^63-1的整數值。

JSON格式：數字

**文字表示**

```json
<integer value>
```

**範例**

```json
42
```

## 小數 {#decimal}

**說明**

小數位數. 它表示浮動值：

* 雙型(2-2^-52)x2^1023的最大正有限值
* 雙，2-1022型的最小正法值
* 雙型最小正非零值，2 p-1074

JSON格式：數字

序列化格式：使用「。」 小數分隔符。

**文字表示**

```json
<integer value>.<integer value>
```

**範例**

```json
3.14
```

## 布林值 {#boolean}

**說明**

寫入的布爾值小寫：真或假

JSON格式：布爾型

**文字表示**

```json
true
```

```json
false
```

**範例**

```json
true
```

## 僅日期 {#date-only}

**說明**

表示僅不帶時區的日期，視為年月日。

它是日期的描述，用於生日。

JSON格式：字串。

格式為：YYYY-MM-DD(ISO-8601)，例如：「2021-03-11」。

它可以封裝在toDateOnly函式中。

它使用DateTimeFormatter ISO_LOCAL_DATE_TIME反序列化和序列化值。 [了解更多](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6)

**文字表示**

```json
date("<dateOnly in ISO-8601 format>")  
```

**範例**

```json
date("2021-02-19")
```

## 日期僅時間 {#date-time-only}

**說明**

表示沒有時區的日期時間，視為年月日時分秒秒。

JSON格式：字串。

它不儲存或表示時區。 相反，它是對生日日期的描述，與牆上鐘上的當地時間相結合。

如果沒有其他資訊（如偏移或時區），則不能表示時間線上的即時。

它可以封裝在toDateTimeOnly函式中。

序列化格式：ISO-8601擴展偏移日期 — 時間格式。

它使用DateTimeFormatter ISO_LOCAL_DATE_TIME反序列化和序列化值。 [了解更多](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**文字表示**

```json
date("<dateTimeOnly in ISO-8601 format>")  
```

**範例**

```json
date("2021-02-19T00.00.000")
date("2021-02-19T00.00")
```

## 日期時間 {#date-time}

**說明**

同時考慮時區的日期時間常數。 它表示具有UTC偏移的日期時間。

可以利用偏移的附加資訊，將其視為即時。 這是在世界某個地方代表一個特定「時刻」的一種方式。

JSON格式：字串。

它可以封裝在toDateTime函式中。

序列化格式：ISO-8601擴展偏移日期 — 時間格式。

它使用DateTimeFormatter ISO_OFFSET_DATE_TIME反序列化和序列化值。 [了解更多](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

也可以傳遞傳遞歷元值的整數。 [閱讀全文](https://www.epochconverter.com)

時區可以由偏移或時區代碼指定(例如：歐洲/巴黎，Z — 表示UTC)。

**文字表示**

```json
toDateTime("<dateTime in ISO-8601 format>")
```

```json
date("<dateTime in ISO-8601 format>")
```

```json
toDateTime(<integer value of an epoch in milliseconds>)
```

**範例**

```json
date("2021-02-19T00.00.000Z")
```

```json
toDateTime("1977-04-22T06:00:00Z")
```

```json
toDateTime("2011-12-03T15:15:30Z")
```

```json
toDateTime("2011-12-03T15:15:30.123Z")
```

```json
toDateTime("2011-12-03T15:15:30.123+02:00")
```

```json
toDateTime("2011-12-03T15:15:30.123-00:20")
```

```json
toDateTime(1560762190189)
```

## 持續時間 {#duration}

**說明**

它表示基於時間的時間量，如「34.5秒」。 它以毫秒為單位來建模數量或時間量。

支援的臨時單位為：毫秒、秒、分鐘、小時、一天等於24小時的天數。 不支援年和月，因為它們不是固定的時間。

JSON格式：字串。

必須將其封裝在toDuration函式中。

序列化格式：要反序列化時區ID，它使用java函式java.time。

持續時間.parse:接受的格式基於ISO-8601持續時間格式PnDTnHnMn.nS，天數被認為恰好為24小時。 [了解更多](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**文字表示**

```json
toDuration("<duration in ISO-8601 format>")
```

```json
toDuration(<duration in milliseconds>)
```

**範例**

```json
toDuration("PT5S") -- parses as 5 seconds
```

```json
toDuration(500) -- parses as 500ms
```

```json
toDuration("PT20.345S") -- parses as "20.345 seconds"
```

```json
toDuration("PT15M") -- parses as "15 minutes" (where a minute is 60 seconds)
```

```json
toDuration("PT10H")  -- parses as "10 hours" (where an hour is 3600 seconds)
```

```json
toDuration("P2D") -- parses as "2 days" (where a day is 24 hours or 86400 seconds)
```

```json
toDuration("P2DT3H4M") -- parses as "2 days, 3 hours and 4 minutes"
```

```json
toDuration("P-6H3M") -- parses as "-6 hours and +3 minutes"
```

```json
toDuration("-P6H3M") -- parses as "-6 hours and -3 minutes"
```

```json
toDuration("-P-6H+3M") -- parses as "+6 hours and -3 minutes"
```

## list {#list}

**說明**

使用方括弧作為分隔符的表達式的逗號分隔清單。

不支援多態性，因此清單中包含的所有表達式應具有相同的類型。

**文字表示**

```json
[<expression>, <expression>, ... ]
```

**範例**

```json
["value1","value2"]
```

```json
[3,5]
```

```json
[toDuration(500),toDuration(800)]
```
