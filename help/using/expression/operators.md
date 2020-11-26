---
product: adobe campaign
solution: Journey Orchestration
title: 運算子
description: 瞭解進階運算式中的運算元
translation-type: tm+mt
source-git-commit: 20498e89eb9c95dd19a11e42150a0bbf67024f67
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 5%

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

## 邏輯  {#logical}

### 和

**常值運算式**

```<expression1> and <expression2>```

&lt;expression1>和&lt;expression2>都必須是布林值。 結果是布爾型的。

**範例**

```3.14 > 2 and 3.15 < 1```

### 或

**常值運算式**

```<expression1> or <expression2>```

&lt;expression1>和&lt;expression2>都必須是布林值。 結果是布爾型的。

**範例**

```3.14 > 2 or 3.15 < 1```

### not

**常值運算式**

```not <expression>```

&lt;expression>必須是布林值。 結果是布爾型的。

**範例**

```not 3.15 < 1```

## 比較 {#comparison}

### 為null

**常值運算式**

```<expression> is null```

結果是布爾型的。

請注意，null表示運算式沒有評估值。

**範例**

```@{BarBeacon.location} is null```

### 非null

**常值運算式**

```<expression> is not null```

結果是布爾型的。

請注意，null表示運算式沒有評估值。

**範例**

```@ is not null```

### 具有空值

**常值運算式**

```<expression> has null```

&lt;expression>必須是清單。 結果是布爾型的。

用於識別清單至少包含一個空值。

**範例**

```["foo", "bar", null] has null``` 傳回true。

```["foo", "bar", ""] has null``` 傳回false，因為&quot;&quot;不被視為null。

### ==

**常值運算式**

```<expression1> == <expression2>```

&lt;expression1>和&lt;expression2>必須具有相同的資料類型。 結果是布爾型的。

**範例**

```3.14 == 42```

```"foo" == "bar"```

### !=

**常值運算式**

```<expression1> != <expression2>```

&lt;expression1>和&lt;expression2>必須具有相同的資料類型。 結果是布爾型的。

**範例**

```3.14 != 42```

```"foo" != "bar"```

### >

**常值運算式**

```<expression1> > <expression2>```

可以將日期時間與日期時間進行比較。

Datetimeonly可與Datetimeonly比較。

整數或小數都可與整數或小數進行比較。

任何其他組合都禁止使用。

結果是布爾型的。

**範例**

```3.14 > 42```

### >=

**常值運算式**

```<expression1> >= <expression2>```

可以將日期時間與日期時間進行比較。

Datetimeonly可與Datetimeonly比較。

整數或小數都可與整數或小數進行比較。

任何其他組合都禁止使用。

結果是布爾型的。

**範例**

```42 >= 3.14```

### &lt;

**常值運算式**

```<expression1> < <expression2>```

可以將日期時間與日期時間進行比較。

Datetimeonly可與Datetimeonly比較。

整數或小數都可與整數或小數進行比較。

任何其他組合都禁止使用。

結果是布爾型的。

**範例**

```42 < 3.14```

### &lt;=

**常值運算式**

```<expression1> <= <expression2>```

可以將日期時間與日期時間進行比較。

Datetimeonly可與Datetimeonly比較。

整數或小數都可與整數或小數進行比較。

任何其他組合都禁止使用。

結果是布爾型的。

**範例**

```42 <= 3.14```

## 算術 {#arithmetic}

### +

**常值運算式**

```<expression1> + <expression2>```

這兩個運算式都必須是數值（整數或小數）。

結果也是數值。

**範例**

```1 + 2``` 返回3

### -

**常值運算式**

```<expression1> - <expression2>```

這兩個運算式都必須是數值（整數或小數）。

結果也是數值。

**範例**

```2 - 1``` 返回1

### /

**常值運算式**

```<expression1> / <expression2>```

這兩個運算式都必須是數值（整數或小數）。

結果也是數值。

&lt;expression2>不能等於0（傳回0）。

**範例**

```4 / 2``` 返回2

### *

**常值運算式**

```<expression1> * <expression2>```

這兩個運算式都必須是數值（整數或小數）。

結果也是數值。

**範例**

```3 * 4``` 返回12

### %

**常值運算式**

```<expression1> % <expression2>```

這兩個運算式都必須是數值（整數或小數）。

結果也是數值。

**範例**

```3 % 2``` 返回1。

## 數學 {#math}

### 數值

**常值運算式**

```<expression> is numeric```

運算式的類型為整數或小數。

**範例**

```@ is numeric```

### 整數

**常值運算式**

```<expression> is integer```

運算式的類型為整數。

**範例**

```@ is integer```

### 小數點

**常值運算式**

```<expression> is decimal```

表達式的類型為十進位。

**範例**

```@ is decimal```

## String {#string}

### +

**常值運算式**

```<string> + <expression>```

```<expression> + <string>```

它串連兩個運算式。

一個運算式必須是連結字串。

**範例**

```"the current time is " + (now())``` 傳回「目前時間為2019-09-23T09:30:06.693Z」

```(now()) + " is the current time"``` 傳回&quot;2019-09-23T09:30:06.693Z是目前時間&quot;

```"a" + "b" + "c" + 1234``` 傳回&quot;abc1234&quot;。

## 日期 {#date}

### +

**常值運算式**

```<expression + <duration>```

將持續時間附加至dateTime、dateTimeOnly或duration。

**範例**

```toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M")``` 返回2011-12-03T15:30:30Z

```toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M")``` 返回2011-12-03T15:30:30

```now() + toDuration("PT1H")``` 傳回自目前時間起1小時後的dateTime（含UTC時區）

```toDuration("PT1H") + toDuration("PT1H")``` 返回PT2H
