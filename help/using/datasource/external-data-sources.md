---
product: adobe campaign
title: '外部資料來源 '
description: '瞭解如何設定外部資料來源 '
feature: Journeys
role: User
level: Intermediate
exl-id: 9b666c15-2215-4ca5-bc72-40109749dc15
source-git-commit: 7805ee4beb056ba84bc994162da2b0e54db60ca3
workflow-type: tm+mt
source-wordcount: '1318'
ht-degree: 93%

---

# 外部資料來源 {#concept_t2s_kqt_52b}

外部資料來源可讓您定義與協力廠商系統的連線，例如使用飯店訂房系統來檢查某人是否已登記客房。與內建的 Adobe Experience Platform 資料來源不同，您可以視需要儘量建立外部資料來源。

支援使用 POST 或 GET 以及傳回 JSON 的 REST API。支援 API 金鑰、基本和自訂驗證模式。

我們以一個氣象 API 服務為例，我想利用它根據即時氣象資料來自訂歷程的行為。

以下是 API 呼叫的兩個範例：

* _https://api.adobeweather.org/weather?city=London,uk&amp;appid=1234_
* _https://api.adobeweather.org/weather?lat=35&amp;lon=139&amp;appid=1234_

此呼叫由主要 URL (_https://api.adobeweather.org/weather_)、兩個參數集 （&quot;city&quot; 代表城市、&quot;lat/long&quot; 代表經緯度）和 API 金鑰 (appid) 組成。

以下是建立和設定新外部資料來源的主要步驟：

1. 從資料來源清單中，按一下 **[!UICONTROL Create data source]** 建立新外部資料來源。

   ![](../assets/journey25.png)

   這會開啟畫面右側的資料來源設定窗格。

   ![](../assets/journey26.png)

1. 輸入您的資料來源名稱。

   >[!NOTE]
   >
   >請勿使用空格或特殊字元。請勿使用超過 30 個字元。

1. 新增說明至您的資料來源。此步驟為選填。
1. 新增外部服務的 URL。在我們的範例中：_https://api.adobeweather.org/weather_。

   >[!CAUTION]
   >
   >基於安全考量，我們強烈建議您使用 HTTPS。另請注意，我們不允許使用非公開的 Adobe 網址和 IP 位址。

   ![](../assets/journey27.png)

1. 根據外部服務配置設定身份驗證：**[!UICONTROL No authentication]**、**[!UICONTROL Basic]**、**[!UICONTROL Custom]** 或 **[!UICONTROL API key]**。如需自訂驗證模式的詳細資訊，請參閱 [本節](../datasource/external-data-sources.md#section_wjp_nl5_nhb). 在我們的範例中，我們選擇：


   * **[!UICONTROL Type]**：&quot;API key&quot;
   * **[!UICONTROL Value]**：&quot;1234&quot;（這是我們 API 金鑰的值）
   * **[!UICONTROL Name]**：&quot;appid&quot;（這是 API 金鑰參數名稱）
   * **[!UICONTROL Location]**：&quot;Query parameter&quot;（API 金鑰位於 URL）

   ![](../assets/journey28.png)

1. 按一下 **[!UICONTROL Add a New Field Group]**，為每個 API 參數集新增欄位群組。請勿在欄位群組名稱中使用空格或特殊字元。在我們的範例中，我們需要建立兩個欄位群組，每個群各有一個參數集（city 及 long/lat）。

在 &quot;long/lat&quot; 參數集中，我們會建立包含下列資訊的欄位群組：

* **[!UICONTROL Used in]**：顯示使用欄位群組的歷程數量。您可以按一下 **[!UICONTROL View journeys]** 圖示，以顯示使用此欄位群組的歷程清單。
* **[!UICONTROL Method]**：選取 POST 或 GET 方法。在本例中，我們選取 GET 方法。
* **[!UICONTROL Response Payload]**：在 **[!UICONTROL Payload]** 欄位內按一下，並貼上呼叫傳回之有效負載的範例。例如，我們使用了氣象 API 網站上找到的有效負載。確認欄位類型是否正確。每次呼叫 API 時，系統都會擷取有效負載範例中包含的所有欄位。請注意，您可以按一下 **[!UICONTROL Paste a new payload]**，以變更目前已傳遞的有效負載。
* **[!UICONTROL Dynamic Values]**：在本例中，輸入以逗號分隔的不同參數，即 &quot;long,lat&quot;。由於參數值視執行內容而定，因此它們會在歷程中定義。請參閱[此頁面](../expression/expressionadvanced.md)。
* **[!UICONTROL Sent Payload]**：我們的範例不會出現此欄位，只有選取 POST 方法時才能使用。貼上會傳送至協力廠商系統的有效負載。

若是 GET 呼叫所需的參數，您會在 **[!UICONTROL Dynamic Values]** 欄位中輸入參數，系統就會在呼叫結束時自動新增這些參數。若是 POST 呼叫，您需要：

* 在 **[!UICONTROL Dynamic Values]** 欄位中列出呼叫時要傳遞的參數（在以下範例中：“identifier”）。
* 在已傳送有效負載的正文中，也使用完全相同的語法指定它們。若要這麼做，您必須新增：&quot;param&quot;: “name of your parameter”（在以下範例中：“identifier”）。請遵循下列語法：

   ```
   {"id":{"param":"identifier"}}
   ```

![](../assets/journey29.png)

按一下「**[!UICONTROL Save]**」。

資料來源現在已設定完畢，且可供您在歷程中使用，例如在您的條件或個人化電子郵件中。如果溫度超過 30°C，您可以決定傳送特定通訊。

## 自訂驗證模式{#section_wjp_nl5_nhb}

>[!CONTEXTUALHELP]
>id="jo_authentication_payload"
>title="關於自訂驗證"
>abstract="自訂驗證模式會用於複雜驗證，以呼叫 OAuth2 這類 API 封裝通訊協定。動作執行是兩個步驟的流程。首先，系統會執行端點呼叫以產生存取權杖。接著，存取權杖會插入到動作的 HTTP 要求中。"

此驗證模式會用於複雜驗證，常用來呼叫 OAuth2 這類 API 封裝通訊協定，以擷取要插入到動作之實際 HTTP 要求中的存取權杖。

當您設定自訂驗證時，可以按一下下方的按鈕，以檢查自訂驗證有效負載是否已正確設定。

![](../assets/journey29-bis.png)

如果測試成功，按鈕就會變成綠色。

![](../assets/journey29-ter.png)

使用此驗證的話，動作執行會是兩個步驟的流程：

1. 呼叫端點以產生存取權仗。
1. 以正確的方式插入存取權仗來呼叫 REST API。

此驗證分為兩個部分。

要呼叫的端點定義，用於產生存取權仗：

* 端點：用於產生端點的 URL
* 端點上的 HTTP 要求方法（GET 或 POST）
* 標題：在此呼叫中插入做為標題的金鑰/值配對 (若有需要)
* 正文：說明方法為 POST 時呼叫的正文。我們支援有限的正文結構，如 bodyParams (金鑰/值配對) 中所定義。bodyType 說明了呼叫內正文的格式和編碼：
   * &#39;form&#39;：表示內容類型將會是 application/x-www-form-urlencoded（字元集 UTF-8），而金鑰/值配對將會序列化為：key1=value1&amp;key2=value2&amp;...
   * &#39;json&#39;：表示內容類型將會是 application/json（字元集 UTF-8），而金鑰/值配對將會序列化為 JSON 物件，如下所示：_{ &quot;key1&quot;: &quot;value1&quot;, &quot;key2&quot;: &quot;value2&quot;, ...}_

存取權杖插入動作之 HTTP 要求必須採用的方法定義：

* authorizationType：定義如何將產生的存取權杖插入到動作的 HTTP 要求。可能的值包括：

   * bearer：表示存取權杖必須插入到「授權」標題，例如：_Authorization: Bearer &lt;access token>_
   * header：表示存取權杖必須插入為標題，而標題的名稱會用屬性 tokenTarget 定義。舉例來說，若 tokenTarget 是 myHeader，則存取權杖會插入為標題，如下所示：_myHeader: &lt;access token>_
   * queryParam：表示存取權杖必須插入為 queryParam，而查詢參數的名稱會由屬性 tokenTarget 定義。舉例來說，若 tokenTarget 是 myQueryParam，則動作呼叫的 URL 將會是：_&lt;url>?myQueryParam=&lt;access token>_

* tokenInResponse：表示如何從驗證呼叫中擷取存取權杖。此屬性可以是：
   * &#39;response&#39;：表示 HTTP 回應就是存取權杖
   * JSON 的選擇器（假設回應為 JSON，我們不支援 XML 等其他格式）。此選擇器的格式為 _json://&lt;path to the access token property>_。舉例來說，若呼叫的回應是：_{ &quot;access_token&quot;: &quot;theToken&quot;, &quot;timestamp&quot;: 12323445656 }_，tokenInResponse 將會是：_json: //access_token_

此驗證的格式為：

```
{
    "type": "customAuthorization",
    "authorizationType": "<value in 'bearer', 'header' or 'queryParam'>",
    (optional, mandatory if authorizationType is 'header' or 'queryParam') "tokenTarget": "<name of the header or queryParam if the authorizationType is 'header' or 'queryParam'>",
    "endpoint": "<URL of the authentication endpoint>",
    "method": "<HTTP method to call the authentication endpoint, in 'GET' or 'POST'>",
    (optional) "headers": {
        "<header name>": "<header value>",
        ...
    },
    (optional, mandatory if method is 'POST') "body": {
        "bodyType": "<'form'or 'json'>,
        "bodyParams": {
            "param1": value1,
            ...

        }
    },
    "tokenInResponse": "<'response' or json selector in format 'json://<field path to access token>'"
}
```

您可以針對自訂驗證資料來源變更權杖之快取期間的資訊。以下是自訂驗證有效負載的範例。會在　&quot;cacheDuration&quot;　參數中定義快取期間。其會指定快取中產生權杖的保留期間。單位可能是毫秒、秒、分鐘、小時、天、月、年。

```
"authentication": {
    "type":"customAuthorization",
    "authorizationType":"Bearer",
    "endpoint":"http://localhost:${port}/epsilon/oauth2/access_token",
    "method":"POST",
    "headers": {
        "Authorization":"Basic EncodeBase64(${epsilonClientId}:${epsilonClientSecret})"
        },
    "body": {
        "bodyType":"form",
        "bodyParams": {
             "scope":"cn mail givenname uid employeeNumber",
             "grant_type":"password",
             "username":"${epsilonUserName}",
             "password":"${epsilonUserPassword}"
             }
        },
    "tokenInResponse":"json://access_token",
    "cacheDuration":
             { "duration":5, "timeUnit":"seconds" }
    }
```

>[!NOTE]
>
>快取持續時間有助於避免對驗證端點發出太多呼叫。 Authentication token retention is cached in services, there is no persistence. 如果服務重新啟動，則會以乾淨的快取開始。 預設的快取持續時間為1小時。 在自訂動作裝載中，可指定其他保留期間來調整它。