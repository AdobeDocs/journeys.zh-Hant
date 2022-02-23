---
product: adobe campaign
title: 操作者
description: 瞭解高級表達式中的運算子
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: fd86b6ab-76cf-4b35-9e87-f441e914f20b
source-git-commit: a0b6ab595bc16a75aa5a56a858900418e2381ab9
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 7%

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

## 重要備註{#important-notes}

* 使用乘法時(`*`)，兩個操作欄位必須具有相同的類型（整數或小數）。 範例 :
   * 以下示例正確： `3.0 * 4.0`
   * `3 * 4.0` 將導致錯誤

## 邏輯  {#logical}

### 和

```json
<expression1> and <expression2>
```

兩者 &lt;expression1> 和 &lt;expression2> 必須是布爾型。 結果為布爾型。

範例：

```json
3.14 > 2 and 3.15 < 1
```

### 或



```json
<expression1> or <expression2>
```

兩者 &lt;expression1> 和 &lt;expression2> 必須是布爾型。 結果為布爾型。

範例：

```json
3.14 > 2 or 3.15 < 1
```

### 不



```json
not <expression>
```

&lt;expression> 必須是布爾型。 結果為布爾型。

範例：

```json
not 3.15 < 1
```

## 比較 {#comparison}

### 空



```json
<expression> is null
```

結果為布爾型。

請注意，null表示表達式沒有計算值。

範例：

```json
@{BarBeacon.location} is null
```

### 不為空



```json
<expression> is not null
```

結果為布爾型。

請注意，null表示表達式沒有計算值。

範例：

```json
@ is not null
```

### 空



```json
<expression> has null
```

&lt;expression> 必須是清單。 結果為布爾型。

用於標識清單至少包含一個空值。

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

兩者 &lt;expression1> 和 &lt;expression2> 必須具有相同的資料類型。 結果為布爾型。

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

兩者 &lt;expression1> 和 &lt;expression2> 必須具有相同的資料類型。 結果為布爾型。

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

只能將DatetimeOnly與DatetimeOnly進行比較。

整數或小數都可以與整數或小數進行比較。

任何其他組合都是禁止的。

結果為布爾型。

範例：

```json
3.14 > 42
```

### >=



```json
<expression1> >= <expression2>
```

可以將日期時間與日期時間進行比較。

只能將DatetimeOnly與DatetimeOnly進行比較。

整數或小數都可以與整數或小數進行比較。

任何其他組合都是禁止的。

結果為布爾型。

範例：

```json
42 >= 3.14
```

### &lt;



```json
<expression1> < <expression2>
```

可以將日期時間與日期時間進行比較。

只能將DatetimeOnly與DatetimeOnly進行比較。

整數或小數都可以與整數或小數進行比較。

任何其他組合都是禁止的。

結果為布爾型。

範例：

```json
42 < 3.14
```

### &lt;=



```json
<expression1> <= <expression2>
```

可以將日期時間與日期時間進行比較。

只能將DatetimeOnly與DatetimeOnly進行比較。

整數或小數都可以與整數或小數進行比較。

任何其他組合都是禁止的。

結果為布爾型。

範例：

```json
42 <= 3.14
```

## 算術 {#arithmetic}

### +



```json
<expression1> + <expression2>
```

這兩個表達式都必須是數字（整數或小數）。

結果也是數字。

範例：

```json
1 + 2 -- returns 3
```

### -



```json
<expression1> - <expression2>
```

這兩個表達式都必須是數字（整數或小數）。

結果也是數字。

範例：

```json
2 - 1 -- returns 1
```

### /



```json
<expression1> / <expression2>
```

這兩個表達式都必須是數字（整數或小數）。

結果也是數字。

&lt;expression2> 不能等於0（返回0）。

範例：

```json
4 / 2 -- returns 2
```

### *



```json
<expression1> * <expression2>
```

這兩個表達式都必須是數字（整數或小數）。

結果也是數字。

範例：

```json
3 * 4 -- returns 12
```

### %



```json
<expression1> % <expression2>
```

這兩個表達式都必須是數字（整數或小數）。

結果也是數字。

範例：

```json
3 % 2 -- returns 1.
```

## Math {#math}

### 是數字



```json
<expression> is numeric
```

表達式的類型為整數或十進位。

範例：

```json
@ is numeric
```

### 整數



```json
<expression> is integer
```

表達式的類型為整數。

範例：

```json
@ is integer
```

### 小數



```json
<expression> is decimal
```

表達式的類型為十進位。

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

它連接兩個表達式。

一個表達式必須是連結字串。

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

## 日期 {#date}

### +



```json
<expression> + <duration>
```

將持續時間追加到dateTime、dateTimeOnly或duration。

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
