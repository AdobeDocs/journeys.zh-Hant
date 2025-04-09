---
product: adobe campaign
title: 資料類型
description: 瞭解進階運算式中的資料型別
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 343f61b8-2315-4971-8b2b-6aa815bd9ced
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 5%

---

# 資料類型 {#concept_gp3_rj5_dgb}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_


技術上，常數一律包含資料型別。 在常值運算式中，我們僅指定值。 資料型別可從值推斷（例如字串、整數、小數等）。 對於日期時間等特定情況，我們會使用專用功能進行表示。

以下各節提供不同資料型別運算式及其表示方式的資訊。

## 字串 {#string}

**說明**

常見的字元順序。 除了來自環境的隱含大小（例如可用的記憶體數量）外，它沒有任何特定大小。

JSON格式：字串

序列化格式： UTF-8

**常值表示**

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

**常值表示**

```json
<integer value>
```

**範例**

```json
42
```

## 小數 {#decimal}

**說明**

十進位數字。 它代表浮點數值：

* 型別double的最大正有限值， (2-2^-52)x2^1023
* 型別double的最小正常數值，2-1022
* 型別double的最小正非零值，2 p-1074

JSON格式：數字

序列化格式：使用「。」 作為小數分隔符號。

**常值表示**

```json
<integer value>.<integer value>
```

**範例**

```json
3.14
```

## 布林值 {#boolean}

**說明**

布林值會寫入小寫： true或false

JSON格式：布林值

**常值表示**

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

## dateOnly {#date-only}

**說明**

只代表沒有時區的日期，以年 — 月 — 日檢視。

這是日期的說明，用於生日。

JSON格式：字串。

格式為：YYYY-MM-DD (ISO-8601)，例如：「2021-03-11」。

它可以封裝在toDateOnly函式中。

它會使用DateTimeFormatter ISO_LOCAL_DATE_TIME將值還原序列化及序列化。 [了解更多](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6)

**常值表示**

```json
date("<dateOnly in ISO-8601 format>")  
```

**範例**

```json
date("2021-02-19")
```

## dateTimeOnly {#date-time-only}

**說明**

代表沒有時區的日期時間，以年 — 月 — 日 — 小時 — 分鐘 — 秒 — 毫秒的方式檢視。

JSON格式：字串。

它不會儲存或表示時區。 相反地，它是日期的描述（如生日所用），與牆上時鐘所顯示的當地時間相結合。

若沒有位移或時區等額外資訊，它就無法代表時間軸上的瞬間。

它可以封裝在toDateTimeOnly函式中。

序列化格式： ISO-8601延伸位移日期 — 時間格式。

它會使用DateTimeFormatter ISO_LOCAL_DATE_TIME將值還原序列化及序列化。 [了解更多](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**常值表示**

```json
date("<dateTimeOnly in ISO-8601 format>")  
```

**範例**

```json
date("2021-02-19T00.00.000")
date("2021-02-19T00.00")
```

## dateTime {#date-time}

**說明**

也會考量時區的日期時間常數。 它表示與UTC有偏移的日期時間。

它可視為具有位移之其他資訊的即時狀態。 這是一種表示世界上某個地方特定「時刻」的方式。

JSON格式：字串。

它可以封裝在toDateTime函式中。

序列化格式： ISO-8601延伸位移日期 — 時間格式。

它使用DateTimeFormatter ISO_OFFSET_DATE_TIME將值還原序列化和序列化。 [了解更多](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

您也可以傳遞一個傳遞epoch值的整數。 [閱讀全文](https://www.epochconverter.com)

時區可由位移或時區代碼指定（例如：歐洲/巴黎，Z — 表示UTC）。

**常值表示**

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

## 期間 {#duration}

**說明**

這表示以時間為基礎的時間量，例如「34.5秒」。 它會以毫秒為單位模擬時間量或時間量。

支援的暫時單位為：毫秒、秒、分鐘、小時、天，其中一天等於24小時。 不支援年和月，因為它們不是固定的時間量。

JSON格式：字串。

它必須封裝在toDuration函式中。

序列化格式：若要將時區ID還原序列化，會使用java函式java.time。

Duration.parse：接受的格式是以ISO-8601持續時間格式PnDTnHnMn.nS為基礎，天數被視為剛好24小時。 [了解更多](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**常值表示**

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

以逗號分隔的運算式清單，使用方括弧做為分隔符號。

不支援多型，因此清單中包含的所有運算式都應該有相同的型別。

**常值表示**

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
