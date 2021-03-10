---
product: adobe campaign
solution: Journey Orchestration
title: 運算子
description: 瞭解進階運算式中的運算元
feature: 旅程
role: 資料工程師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 6%

---



# 運算子 {#concept_wd5_pj5_dgb}

運算子有兩種：一元運算子和二進位運算子。 有左手一元運算子和右手一元運算子。

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

## 邏輯{#logical}

### 和

```
<expression1> and <expression2>
```

&lt;expression1>和&lt;expression2>都必須是布林值。 結果是布爾型的。

範例:

```
3.14 > 2 and 3.15 < 1
```

### 或



```
<expression1> or <expression2>
```

&lt;expression1>和&lt;expression2>都必須是布林值。 結果是布爾型的。

範例:

```
3.14 > 2 or 3.15 < 1
```

### not



```
not <expression>
```

&lt;expression> 必須是布林值。結果是布爾型的。

範例:

```
not 3.15 < 1
```

## 比較{#comparison}

### 為null



```
<expression> is null
```

結果是布爾型的。

請注意，null表示運算式沒有評估值。

範例:

```
@{BarBeacon.location} is null
```

### 非null



```
<expression> is not null
```

結果是布爾型的。

請注意，null表示運算式沒有評估值。

範例:

```
@ is not null
```

### 具有空值



```
<expression> has null
```

&lt;expression> 必須是清單。結果是布爾型的。

用於識別清單至少包含一個空值。

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

&lt;expression1>和&lt;expression2>必須具有相同的資料類型。 結果是布爾型的。

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

&lt;expression1>和&lt;expression2>必須具有相同的資料類型。 結果是布爾型的。

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

Datetimeonly可與Datetimeonly比較。

整數或小數都可與整數或小數進行比較。

任何其他組合都禁止使用。

結果是布爾型的。

範例:

```
3.14 > 42
```

### >=



```
<expression1> >= <expression2>
```

可以將日期時間與日期時間進行比較。

Datetimeonly可與Datetimeonly比較。

整數或小數都可與整數或小數進行比較。

任何其他組合都禁止使用。

結果是布爾型的。

範例:

```
42 >= 3.14
```

### &lt;>



```
<expression1> < <expression2>
```

可以將日期時間與日期時間進行比較。

Datetimeonly可與Datetimeonly比較。

整數或小數都可與整數或小數進行比較。

任何其他組合都禁止使用。

結果是布爾型的。

範例:

```
42 < 3.14
```

### &lt;>



```
<expression1> <= <expression2>
```

可以將日期時間與日期時間進行比較。

Datetimeonly可與Datetimeonly比較。

整數或小數都可與整數或小數進行比較。

任何其他組合都禁止使用。

結果是布爾型的。

範例:

```
42 <= 3.14
```

## 算術{#arithmetic}

### +



```
<expression1> + <expression2>
```

這兩個運算式都必須是數值（整數或小數）。

結果也是數值。

範例:

```
1 + 2 -- returns 3
```

### -



```
<expression1> - <expression2>
```

這兩個運算式都必須是數值（整數或小數）。

結果也是數值。

範例:

```
2 - 1 -- returns 1
```

### /



```
<expression1> / <expression2>
```

這兩個運算式都必須是數值（整數或小數）。

結果也是數值。

&lt;expression2> 不得等於0（返回0）。

範例:

```
4 / 2 -- returns 2
```

### *



```
<expression1> * <expression2>
```

這兩個運算式都必須是數值（整數或小數）。

結果也是數值。

範例:

```
3 * 4 -- returns 12
```

### %



```
<expression1> % <expression2>
```

這兩個運算式都必須是數值（整數或小數）。

結果也是數值。

範例:

```
3 % 2 -- returns 1.
```

## 數學 {#math}

### 數值



```
<expression> is numeric
```

運算式的類型為整數或小數。

範例:

```
@ is numeric
```

### 整數



```
<expression> is integer
```

運算式的類型為整數。

範例:

```
@ is integer
```

### 小數點



```
<expression> is decimal
```

表達式的類型為十進位。

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

一個運算式必須是連結字串。

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

將持續時間附加至dateTime、dateTimeOnly或duration。

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
