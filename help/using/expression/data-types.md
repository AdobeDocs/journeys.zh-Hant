---
product: adobe campaign
title: 資料類型
description: 了解進階運算式中的資料類型
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 343f61b8-2315-4971-8b2b-6aa815bd9ced
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 5%

---

# 資料類型 {#concept_gp3_rj5_dgb}

技術上，常數一律包含資料類型。 在常值運算式中，我們只指定值。 資料類型可從值推斷（例如字串、整數、小數等）。 對於日期時間等特定案例，我們會使用專屬函式來表示。

以下各節提供不同資料類型運算式的相關資訊，以及其呈現方式。

## 字串 {#string}

**說明**

常見的字元順序。 除了來自環境（如可用記憶體量）的隱式大小外，它沒有任何特定大小。

JSON格式：字串

序列化格式：UTF-8

**常值表示**

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

從–2^63到2^63-1的整數值。

JSON格式：數字

**常值表示**

```
<integer value>
```

**範例**

```
42
```

## 小數 {#decimal}

**說明**

小數位數。 其代表浮動值：

* 雙型最大正有限值，(2-2^-52)x2^1023
* 雙型最小正常值，2-1022
* 雙型最小正非零值，2 p-1074

JSON格式：數字

序列化格式：使用「。」 作為小數分隔符號。

**常值表示**

```
<integer value>.<integer value>
```

**範例**

```
3.14
```

## 布林值 {#boolean}

**說明**

寫入為小寫的布爾值：true或false

JSON格式：布林值

**常值表示**

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

## dateTimeOnly {#date-time-only}

**說明**

表示沒有時區的日期時間，視為年月日、小時、分鐘、毫秒。

不會儲存或代表時區。 相反，它是日期的描述（用於生日），與掛鐘上顯示的當地時間相結合。

若沒有額外資訊（例如位移或時區），則無法呈現時間線上的即時。

序列化格式：ISO-8601延長偏移日期時間格式。

它使用DateTimeFormatter ISO_LOCAL_DATE_TIME反序列化和序列化值。 [瞭解更多](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**常值表示**

```
toDateTimeOnly("<dateTimeOnly in ISO-8601 format>")  
```

## dateTime {#date-time}

**說明**

也會考量時區的日期時間常數。 它表示日期時間，與UTC的偏移。

它可以及時地視為即時，並包含偏移的其他資訊。 這是一種在世界某個地方代表一個特定「時刻」的方式。

JSON格式：字串。

它必須封裝在toDateTime函式中。

序列化格式：ISO-8601延長偏移日期時間格式。

它使用DateTimeFormatter ISO_OFFSET_DATE_TIME反序列化和序列化值。 [瞭解更多](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

您也可以傳遞一個傳遞Epoch值的整數。 [顯示全文](https://www.epochconverter.com)

時區可由偏移或時區代碼指定(範例：歐洲/巴黎，Z — 表示UTC)。

**常值表示**

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

它代表以時間為基礎的時間量，例如「34.5秒」。 它以毫秒為單位來建模數量或時間量。

支援的臨時單元包括：毫秒、秒、分鐘、小時，一天等於24小時的天。 年份和月不受支援，因為它們不是固定的時間。

JSON格式：字串。

它必須封裝在toDuration函式中。

序列化格式：若要反序列化時區ID，會使用java函式java.time。

Duration.parse:接受的格式基於ISO-8601持續時間格式PnDTnHnMn.nS，天數被認為恰好為24小時。 [瞭解更多](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**常值表示**

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

## 清單 {#list}

**說明**

以逗號分隔的運算式清單，以方括弧作為分隔字元。

不支援多態性，因此清單中包含的所有運算式都應具有相同類型。

**常值表示**

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
