---
product: adobe campaign
title: 運算子
description: 了解進階運算式中的運算子
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: fd86b6ab-76cf-4b35-9e87-f441e914f20b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 6%

---

# 運算子 {#concept_wd5_pj5_dgb}

運算子有兩種：一元運算子和二進位運算子。 有左一元運算子和右一元運算子。

```
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

```
<expression1> and <expression2>
```

&lt;expression1>和&lt;expression2>都必須是布林值。 結果為布林值。

範例:

```
3.14 > 2 and 3.15 < 1
```

### 或



```
<expression1> or <expression2>
```

&lt;expression1>和&lt;expression2>都必須是布林值。 結果為布林值。

範例:

```
3.14 > 2 or 3.15 < 1
```

### not



```
not <expression>
```

&lt;expression> 必須是布林值。結果為布林值。

範例:

```
not 3.15 < 1
```

## 比較 {#comparison}

### 為null



```
<expression> is null
```

結果為布林值。

請注意，null表示運算式沒有評估值。

範例:

```
@{BarBeacon.location} is null
```

### 非null



```
<expression> is not null
```

結果為布林值。

請注意，null表示運算式沒有評估值。

範例:

```
@ is not null
```

### 為null



```
<expression> has null
```

&lt;expression> 必須是清單。結果為布林值。

用於識別清單至少包含一個null值。

範例:

```
["foo", "bar", null] has null --  returns true.
```

```
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```
<expression1> == <expression2>
```

&lt;expression1>和&lt;expression2>必須具有相同的資料類型。 結果為布林值。

範例:

```
3.14 == 42
```

```
"foo" == "bar"
```

### !=



```
<expression1> != <expression2>
```

&lt;expression1>和&lt;expression2>必須具有相同的資料類型。 結果為布林值。

範例:

```
3.14 != 42
```

```
"foo" != "bar"
```

### >



```
<expression1> > <expression2>
```

可以將日期時間與日期時間進行比較。

Datetimeonly可與Datetimeonly進行比較。

整數或小數都可與整數或小數進行比較。

禁止使用其他組合。

結果為布林值。

範例:

```
3.14 > 42
```

### >=



```
<expression1> >= <expression2>
```

可以將日期時間與日期時間進行比較。

Datetimeonly可與Datetimeonly進行比較。

整數或小數都可與整數或小數進行比較。

禁止使用其他組合。

結果為布林值。

範例:

```
42 >= 3.14
```

### &lt;>



```
<expression1> < <expression2>
```

可以將日期時間與日期時間進行比較。

Datetimeonly可與Datetimeonly進行比較。

整數或小數都可與整數或小數進行比較。

禁止使用其他組合。

結果為布林值。

範例:

```
42 < 3.14
```

### &lt;>



```
<expression1> <= <expression2>
```

可以將日期時間與日期時間進行比較。

Datetimeonly可與Datetimeonly進行比較。

整數或小數都可與整數或小數進行比較。

禁止使用其他組合。

結果為布林值。

範例:

```
42 <= 3.14
```

## 算術 {#arithmetic}

### +



```
<expression1> + <expression2>
```

這兩個運算式都必須是數值（整數或小數）。

結果也為數值。

範例:

```
1 + 2 -- returns 3
```

### -



```
<expression1> - <expression2>
```

這兩個運算式都必須是數值（整數或小數）。

結果也為數值。

範例:

```
2 - 1 -- returns 1
```

### /



```
<expression1> / <expression2>
```

這兩個運算式都必須是數值（整數或小數）。

結果也為數值。

&lt;expression2> 不得等於0（傳回0）。

範例:

```
4 / 2 -- returns 2
```

### *



```
<expression1> * <expression2>
```

這兩個運算式都必須是數值（整數或小數）。

結果也為數值。

範例:

```
3 * 4 -- returns 12
```

### %



```
<expression1> % <expression2>
```

這兩個運算式都必須是數值（整數或小數）。

結果也為數值。

範例:

```
3 % 2 -- returns 1.
```

## 數學 {#math}

### 為數值



```
<expression> is numeric
```

運算式的類型為整數或小數。

範例:

```
@ is numeric
```

### 為整數



```
<expression> is integer
```

運算式的類型為整數。

範例:

```
@ is integer
```

### 小數



```
<expression> is decimal
```

運算式的類型為小數。

範例:

```
@ is decimal
```

## String {#string}

### +



```
<string> + <expression>
```

```
<expression> + <string>
```

它串連兩個運算式。

一個表達式必須是鏈結字串。

範例:

```
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## 日期 {#date}

### +



```
<expression + <duration>
```

將持續時間附加至dateTime、dateTimeOnly或持續時間。

範例:

```
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
