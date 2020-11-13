---
title: 運算子
description: 瞭解進階運算式中的運算元
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: eec6203f63fa6d7ea706595ea866d2b330d284a8
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 4%

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

## 邏輯

<table>
<thead>
<tr><th>運算元</th><th>常值運算式</th><th>範例</th></tr>
</thead>
<tbody>
<tr><td>和</td><td><p><pre>&lt;expression1&gt;和&lt;expression2&gt;</pre></p>&lt;expression1&gt;和&lt;expression2&gt;都必須是布林值。 結果是布爾型的。</td><td><pre>3.14 &gt; 2和3.15 &lt; 1</pre></td></tr>
<tr><td>或</td><td><p><pre>&lt;expression1&gt;或&lt;expression2&gt;</pre></p><p>&lt;expression1&gt;和&lt;expression2&gt;都必須是布林值。</p><p> 結果是布爾型的。</p></td><td><p><pre>3.14 &gt; 2或3.15 &lt; 1</pre></p></td></tr>
<tr><td>not</td><td><p><pre>not &lt;expression&gt;</pre></p><p>&lt;expression&gt;必須是布林值。</p><p> 結果是布爾型的。</p></td><td><pre>不是3.15 &lt; 1</pre></td></tr>
</tbody>
</table>

## 比較

<table>
<thead>
<tr><th>運算元</th><th>常值運算式 </th><th>範例</th></tr>
</thead>
<tbody><tr><td>為null</td><td><p><pre>&lt;expression&gt;為空</pre></p><p>結果是布爾型的。</p><p>請注意，null表示運算式沒有評估值。</p></td><td><pre>@{BarBeacon.location}為null</pre></td></tr>
<tr><td>非null</td><td><p><pre>&lt;expression&gt;非null</pre></p><p>結果是布爾型的。</p><p>請注意，null表示運算式沒有評估值。</p></td><td><pre>@不為空</pre></td></tr>
<tr><td>具有空值</td><td><p><pre>&lt;expression&gt;包含空值</pre>&lt;expression&gt;必須是清單。</p><p>結果是布爾型的。</p><p>用於識別清單至少包含一個空值。</p></td><td><p><pre>["foo", "bar",null]具有空值</pre></p>返回true<p><pre>["foo"、"bar"、""有空值</pre></p> 傳回false，因為""不被視為null。</td></tr>
<tr><td>==</td><td><p><pre>&lt;expression1&gt; == &lt;expression2&gt;</pre></p><p>&lt;expression1&gt;和&lt;expression2&gt;必須具有相同的資料類型。</p><p> 結果是布爾型的。</p></td><td><pre>3.14 == 42</pre><br /><pre>"foo" == "bar"</pre></td></tr>
<tr><td>!=</td><td><p><pre>&lt;expression1&gt; != &lt;expression2&gt;</pre></p><p> &lt;expression1&gt;和&lt;expression2&gt;必須具有相同的資料類型。</p><p> 結果是布爾型的。</p></td><td><pre>3.14 != 42</pre><br /><pre>"foo" != "bar"</pre></td></tr>
<tr><td>&gt;</td><td><p><pre>&lt;expression1&gt; &gt; &lt;expression2&gt;</pre></p><p>可以將日期時間與日期時間進行比較。</p><p>Datetimeonly可與Datetimeonly比較。</p><p>整數或小數都可與整數或小數進行比較。</p><p>任何其他組合都禁止使用。</p><p>結果是布爾型的。</p></td><td><pre>3.14 &gt; 42</pre></td></tr>
<tr><td>&gt;=</td><td><p><pre>&lt;expression1&gt; &gt;= &lt;expression2&gt;</pre></p><p>可以將日期時間與日期時間進行比較。</p><p>Datetimeonly可與Datetimeonly比較。</p><p>整數或小數都可與整數或小數進行比較。</p><p>任何其他組合都禁止使用。</p><p>結果是布爾型的。</p></td><td><pre>42 &gt;= 3.14</pre></td></tr>
<tr><td>&lt;</td><td><p><pre>&lt;expression1&gt; &lt; &lt;expression2&gt;</pre></p><p>可以將日期時間與日期時間進行比較。</p><p>Datetimeonly可與Datetimeonly比較。</p><p>整數或小數都可與整數或小數進行比較。</p><p>任何其他組合都禁止使用。</p><p>結果是布爾型的。</p></td><td><pre>42 &lt; 3.14</pre></td></tr>
<tr><td>&lt;=</td><td><p><pre>&lt;expression1&gt; &lt;= &lt;expression2&gt;</pre></p><p>可以將日期時間與日期時間進行比較。</p><p>Datetimeonly可與Datetimeonly比較。</p><p>整數或小數都可與整數或小數進行比較。</p><p>任何其他組合都禁止使用。</p><p>結果是布爾型的。</p></td><td><pre>42 &lt;= 3.14</pre></td></tr>
</tbody>
</table>

## 算術

<table>
<thead>
<tr><th>運算元</th><th>常值運算式 </th><th>範例</th></tr>
</thead>
<tbody><tr><td>+</td><td><p><pre>&lt;expression1&gt; + &lt;expression2&gt;</pre></p><p>這兩個運算式都必須是數值（整數或小數）。 </p><p>結果也是數值。</p></td><td><p><p><pre>1 + 2</pre></p></p><br /><p>退貨3</p></td></tr>
<tr><td>-</td><td><p><pre>&lt;expression1&gt; - &lt;expression2&gt;</pre></p><p> 這兩個運算式都必須是數值（整數或小數）。</p><p> 結果也是數值。</p></td><td><p><pre>2 - 1</pre></p>返回1</td></tr>
<tr><td>/</td><td><p><pre>&lt;expression1&gt; / &lt;expression2&gt;</pre></p><p>這兩個運算式都必須是數值（整數或小數）。 </p><p>結果也是數值。</p><p>&lt;expression2&gt;不能等於0（傳回0）。</p></td><td><p><pre>4 / 2</pre></p>退貨2</td></tr>
<tr><td>*</td><td><p><pre>&lt;expression1&gt; * &lt;expression2&gt;</pre></p><p> 這兩個運算式都必須是數值（整數或小數）。 </p><p>結果也是數值。</p></td><td><p><pre>3 * 4</pre></p>退貨12</td></tr>
<tr><td>%</td><td><p><pre>&lt;expression1&gt; % &lt;expression2&gt;</pre></p><p>這兩個運算式都必須是數值（整數或小數）。</p><p> 結果也是數值。</p></td><td><p><pre>3 % 2</pre></p>返回1。</td></tr>
</tbody>
</table>

## 數學

<table>
<thead>
<tr><th>運算元</th><th>常值運算式</th><th>範例</th></tr>
</thead>
<tbody><tr><td>數值</td><td><p><pre>&lt;expression&gt;是數字</pre></p><p>運算式的類型為整數或小數。</p></td><td><pre>@是數字</pre></td></tr>
<tr><td>整數</td><td><p><pre>&lt;expression&gt;為整數</pre></p><p>運算式的類型為整數。</p></td><td><pre>@是整數</pre></td></tr>
<tr><td>小數點</td><td><p><pre>&lt;expression&gt;小數</pre></p><p>表達式的類型為十進位。</p></td><td><pre>@是小數</pre></td></tr>
</tbody>
</table>

## String

<table>
<thead>
<tr><th>運算元</th><th>常值運算式 </th><th>範例</th></tr>
</thead>
<tbody><tr><td>+</td><td><p><pre>&lt;string&gt; + &lt;expression&gt;</pre></p><p><pre>&lt;expression&gt; + &lt;string&gt;</pre></p><p>它串連兩個運算式。 </p><p>一個運算式必須是連結字串。</p></td><td><p><pre>"當前時間是" +(now()))</pre></p> 傳回「目前時間為2019-09-23T09:30:06.693Z」<p><pre>(now())+ "是目前時間"</pre></p>傳回"2019-09-23T09:30:06.693Z是目前時間"<p><pre>"a" + "b" + "c" + 1234</pre></p> 傳回"abc1234"。</td></tr>
</tbody>
</table>

## 日期

<table>
<thead>
<tr><th>運算元</th><th>常值運算式 </th><th>範例</th></tr>
</thead>
<tbody>
<tr><td>+</td><td><p><pre>&lt;expression + &lt;duration&gt;</pre></p><p>將持續時間附加至dateTime、dateTimeOnly或duration。</p></td><td><p><pre>toDateTime("2011-12-03T15:15:30Z")</pre></p><p><pre> + toDuration("PT15M")</pre></p><p>傳回2011-12-03T15:30:30Z</p><p><pre>toDateTimeOnly("2011-12-03T15:15:30")</pre></p><p><pre> + toDuration("PT15M")</pre></p>傳回2011-12-03T15:30:30<p><pre>now()+ toDuration("PT1H")</pre></p><p>傳回自目前時間起1小時後的dateTime（含UTC時區）</p><p><pre>toDuration("PT1H")+ toDuration("PT1H")</pre></p><p>傳回PT2H</p></td></tr>
</tbody>
</table>