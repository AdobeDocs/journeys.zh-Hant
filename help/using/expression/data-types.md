---
title: 資料類型
description: 瞭解進階運算式中的資料類型
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4871550d1608f4ffdee3b56d38b08f808eb2281c
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 3%

---


# 資料類型 {#concept_gp3_rj5_dgb}

從技術上講，常數一律包含資料類型。 在常值運算式中，我們只指定值。 您可從值（例如字串、整數、小數等）推斷資料類型。 對於特定情況（例如日期時間），我們使用專屬函式來表示。

以下是資料類型運算式的表示方式：

<table>
    <thead>
        <tr>
        <td>資料類型</td>
        <td>說明</td>
        <td>常值表示法</td>
        <td>範例</td>
        </tr>
    </thead>
    <tbody>
    <tr>
        <td>字串</td>
        <td><p>常見的字元順序。</p><p>除了來自環境（如可用記憶體量）的隱式大小外，它沒有任何特定大小。</p><p>JSON格式： 字串</p><p>序列化格式： UTF-8</p></td>
        <td><p>"&lt;value&gt;"</p><p>'&lt;value&gt;</p></td>
        <td><p><pre>"hello world"</pre></p><p><pre>'hello world'</pre></p></td>
    </tr>
    <tr>
        <td>整數</td>
        <td><p>從-2^63到2^63-1的整數值。</p><p>JSON格式： 數字</p></td>
        <td>&lt;整數值&gt;</td>
        <td><p><pre>42</pre></p></td>
    </tr>
    <tr>
        <td>小數點</td>
        <td><p>小數。</p><p>它代表浮動值：</p>
        <p>-雙型最大正有限值，(2-2^-52)x2^1023</p>
        <p> -雙類型的最小正常值，2-1022</p>
        <p> -雙類型的最小正非零值，2 p-1074</p><p>JSON格式： 數字</p><p>序列化格式： 使用'.' 作為小數分隔符。</p></td>
        <td>&lt;integer value&gt;。&lt;整數值&gt;</td>
        <td><p><pre>3.14</pre></p></td>
    </tr>
    <tr>
        <td>布林值</td>
        <td><p>寫成小寫的布爾值： true或false</p><p>JSON格式： 布林值</p></td>
        <td><p>true</p><p>false</p></td>
        <td><p><pre>true</pre></p></td>
    </tr>
    <tr>
        <td>dateTimeOnly</td>
        <td><p>表示沒有時區的日期時間，視為年月日每小時每分鐘毫秒。</p><p>它不儲存或表示時區。</p><p>相反，它是日期的描述，如生日所用，加上牆鐘上的當地時間。</p><p>如果沒有偏移或時區等額外資訊，則無法在時線上即時顯示。</p><p>序列化格式： ISO-8601延伸偏移日期——時間格式。</p><p>它使用DateTimeFormatter。</p><p>ISO_LOCAL_DATE_TIME，以反序列化值。</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME">進一步瞭解</a>.</td>
        <td><p>toDateTimeOnly("&lt;dateTimeOnly in ISO-8601 format&gt;")</p></td>
        <td></td>
    </tr>
    <tr>
        <td>dateTime</td>
        <td><p>也會考慮時區的日期時間常數。</p><p>它表示與UTC偏移的日期時間。 它可與偏移的額外資訊即時檢視。 </p><p>這是在世界某個地方代表一個特定「時刻」的一種方式。</p><p>JSON格式： 字串。</p><p> 它必須封裝在toDateTime函式中。</p><p>
        序列化格式： ISO-8601延伸偏移日期——時間格式。</p><p> 它使用DateTimeFormatter.ISO_OFFSET_DATE_TIME反序列化值。</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME">進一步瞭解</a>. 
        <p>您也可以傳遞一個傳遞紀元值的整數。</p> <a href="https://www.epochconverter.com/">瞭解詳情</a>。</p>
        <p>時區可由偏移或時區代碼指定(例如： 歐洲／巴黎， Z —— 意為UTC)。</p></td>
        <td><p>toDateTime（"&lt;ISO-8601格式的dateTime&gt;"）</p>
        <p>toDateTime（&lt;以毫秒為單位的紀元整數值&gt;）</p></td>
        <td><p><pre>toDateTime("1977-04-22T06:00:00Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>(「2011-12-03T15:15:30Z」)</pre></p><p><pre>toDateTime</pre></p><p><pre>(「2011-12-03T15:15:30.123Z」)</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123+02:00")</pre></p>
        <p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123-00:20")</pre></p><p><pre>toDateTime(1560762190189)</pre></p></td>
    </tr>
    <tr>
        <td>持續時間</td>
        <td><p>它代表以時間為基礎的時間量，例如'34.5秒'。</p><p> 它以毫秒為單位來模擬量或時間量。</p><p>支援的臨時單元包括： 毫秒、秒、分鐘、小時、日等於24小時的天數。</p><p> 年份和月份不受支援，因為它們不是固定的時間。</p><p>JSON格式： 字串。 它必須封裝在toDuration函式中。</p><p>序列化格式： 若要反序列化時區ID，它會使用java函式java.time。</p><p>Duration.parse: 接受的格式基於ISO-8601持續時間格式PnDTnHnMn.nS，其天數被認為恰好為24小時。</p><a href="https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-">進一步瞭解</a>.</td>
        <td><p>toDuration（"&lt;ISO-8601格式中的持續時間&gt;"）</p><p>toDuration(&lt;duration in milliseds&gt;)</p></td>
        <td><p><pre>toDuration("PT5S")// 5秒</pre></p>
        <p><pre>toDuration(500)// </pre></p>
        <p><pre>500ms</pre></p>
        <p><pre>toDuration("PT20.345S") </pre></p>
        <p><pre>—解析為"20.345秒"</pre></p>
        <p><pre>toDuration("PT15M") </pre></p>
        <p><pre> —解析為「15分鐘」</pre></p>
        <p><pre>（其中一分鐘是60秒）</pre></p>
        <p><pre>toDuration("PT10H") </pre></p>
        <p><pre>—解析為"10小時"</pre></p>
        <p><pre>（其中一小時為3600秒）</pre></p>
        <p><pre>toDuration("P2D") </pre></p>
        <p><pre>—解析為「2天」</pre></p>
        <p><pre>(其中 </pre></p>
        <p><pre>24小時或86400秒)</pre></p>
        <p><pre>toDuration("P2DT3H4M") </pre></p>
        <p><pre>— Parcas</pre></p>
        <p><pre>"2天，3小時，4分鐘"</pre></p>
        <p><pre>toDuration("P-6H3M") </pre></p>
        <p><pre>— Parcas</pre></p>
        <p><pre>"-6小時+3分鐘"</pre></p>
        <p><pre>toDuration("-P6H3M") </pre></p>
        <p><pre>— Parcas</pre></p>
        <p><pre>"-6小時-3分鐘"</pre></p>
        <p><pre>toDuration("-P-6H+3M") </pre></p>
        <p><pre>— Parcas</pre></p>
        <p><pre>"+6小時和-3分鐘"</pre></p></td>
    </tr>
    <tr>
        <td>清單</td>
        <td>使用方括弧作為分隔字元的運算式清單（以逗號分隔）。 不支援多態性，因此清單中包含的所有表達式都應具有相同類型。</td>
        <td>[&lt;expression&gt;, &lt;expression&gt;, ... ]</td>
        <td><p><pre>["value1","value2"]</pre></p><p><pre>[3,5]</pre></p><p><pre>[toDuration(500),toDuration(800)]</pre></p></td>
    </tr>
    </tbody>
</table>
