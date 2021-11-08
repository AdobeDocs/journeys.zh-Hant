---
product: adobe campaign
title: 操作者
description: 了解進階運算式中的運算子
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: fd86b6ab-76cf-4b35-9e87-f441e914f20b
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 6%

---

# 操作者 {#concept_wd5_pj5_dgb}

運算子有兩種：一元運算子和二進位運算子。 有左一元運算子和右一元運算子。

```json
    // left-hand unary operators
    <operator> <operand> // operand is an expression
    not (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example@adobe.com")

    // right-hand unary operators
    <operand> <operator> // operand is an expression
    @{LobbyBeacon.endUserIDs._experience.emailid.id} is not null

    // binary operators
    <operand1> <operator> <operand2>
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example1@adobe.com") or
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example2@adobe.com")
```

以下是支援的運算子清單：

## 邏輯  {#logical}

### 和

```json
<expression1> and <expression2>
```

兩者 &lt;expression1> 和 &lt;expression2> 必須是布林值。 結果為布林值。

範例：

```json
3.14 > 2 and 3.15 < 1
```

### 或



```json
<expression1> or <expression2>
```

兩者 &lt;expression1> 和 &lt;expression2> 必須是布林值。 結果為布林值。

範例：

```json
3.14 > 2 or 3.15 < 1
```

### not



```json
not <expression>
```

&lt;expression> 必須是布林值。 結果為布林值。

範例：

```json
not 3.15 < 1
```

## 比較 {#comparison}

### 為null



```json
<expression> is null
```

結果為布林值。

請注意，null表示運算式沒有評估值。

範例：

```json
@{BarBeacon.location} is null
```

### 非null



```json
<expression> is not null
```

結果為布林值。

請注意，null表示運算式沒有評估值。

範例：

```json
@ is not null
```

### 為null



```json
<expression> has null
```

&lt;expression> 必須是清單。 結果為布林值。

用於識別清單至少包含一個null值。

範例：

```json
["foo", "bar", null] has null --  returns true.
```

```json
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```json
<expression1> == <expression2>
```

兩者 &lt;expression1> 和 &lt;expression2> 必須具有相同的資料類型。 結果為布林值。

範例：

```json
3.14 == 42
```

```json
"foo" == "bar"
```

### !=



```json
<expression1> != <expression2>
```

兩者 &lt;expression1> 和 &lt;expression2> 必須具有相同的資料類型。 結果為布林值。

範例：

```json
3.14 != 42
```

```json
"foo" != "bar"
```

### >



```json
<expression1> > <expression2>
```

可以將日期時間與日期時間進行比較。

Datetimeonly可與Datetimeonly進行比較。

整數或小數都可與整數或小數進行比較。

禁止使用其他組合。

結果為布林值。

範例：

```json
3.14 > 42
```

### >=



```json
<expression1> >= <expression2>
```

可以將日期時間與日期時間進行比較。

Datetimeonly可與Datetimeonly進行比較。

整數或小數都可與整數或小數進行比較。

禁止使用其他組合。

結果為布林值。

範例：

```json
42 >= 3.14
```

### &lt;



```json
<expression1> < <expression2>
```

可以將日期時間與日期時間進行比較。

Datetimeonly可與Datetimeonly進行比較。

整數或小數都可與整數或小數進行比較。

禁止使用其他組合。

結果為布林值。

範例：

```json
42 < 3.14
```

### &lt;=



```json
<expression1> <= <expression2>
```

可以將日期時間與日期時間進行比較。

Datetimeonly可與Datetimeonly進行比較。

整數或小數都可與整數或小數進行比較。

禁止使用其他組合。

結果為布林值。

範例：

```json
42 <= 3.14
```

## 算術 {#arithmetic}

### +



```json
<expression1> + <expression2>
```

這兩個運算式都必須是數值（整數或小數）。

結果也為數值。

範例：

```json
1 + 2 -- returns 3
```

### -



```json
<expression1> - <expression2>
```

這兩個運算式都必須是數值（整數或小數）。

結果也為數值。

範例：

```json
2 - 1 -- returns 1
```

### /



```json
<expression1> / <expression2>
```

這兩個運算式都必須是數值（整數或小數）。

結果也為數值。

&lt;expression2> 不得等於0（傳回0）。

範例：

```json
4 / 2 -- returns 2
```

### *



```json
<expression1> * <expression2>
```

這兩個運算式都必須是數值（整數或小數）。

結果也為數值。

範例：

```json
3 * 4 -- returns 12
```

### %



```json
<expression1> % <expression2>
```

這兩個運算式都必須是數值（整數或小數）。

結果也為數值。

範例：

```json
3 % 2 -- returns 1.
```

## Math {#math}

### 為數值



```json
<expression> is numeric
```

運算式的類型為整數或小數。

範例：

```json
@ is numeric
```

### 為整數



```json
<expression> is integer
```

運算式的類型為整數。

範例：

```json
@ is integer
```

### 小數



```json
<expression> is decimal
```

運算式的類型為小數。

範例：

```json
@ is decimal
```

## 字串 {#string}

### +



```json
<string> + <expression>
```

```json
<expression> + <string>
```

它串連兩個運算式。

一個表達式必須是鏈結字串。

範例：

```json
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```json
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```json
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## Date {#date}

### +



```json
<expression> + <duration>
```

將持續時間附加至dateTime、dateTimeOnly或持續時間。

範例：

```json
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```json
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```json
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```json
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
