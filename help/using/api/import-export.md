---
title: 匯入匯出API說明
description: 進一步瞭解匯入匯出API。
contentOwner: sauviat
products: journeys
audience: audiences
content-type: reference
topic-tags: journeys
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c92d7a4e5ef02f87f705871cd0fdb8c2523966d2
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 使用匯出匯入API

使用單一API呼叫匯出歷程版本及其所有相關物件（歷程、事件、資料來源、欄位群組、自訂動作）。 匯出產生的裝載可用來輕鬆將歷程匯入其他環境（例項或沙盒）。
此功能可讓您管理多個執行個體或多個測試環境工作流程的歷程。


## 資源

Journey Orchestration Import Export API是在此處提供的Swagger檔案中 [說明](https://adobedocs.github.io/JourneyAPI/docs/)。

若要將此API與您的Journey Orchestration例項搭配使用，您必須使用AdobeI/O Console。 您可以先遵循本「Adobe Developer Console [快速入門」](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) ，然後使用本頁中的章節。

若要測試並準備整合，此處提供Postman [系列](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json)。


## 匯出——匯入流程

我們建議您依照下列步驟，跨環境匯出和匯入您的旅程：

1. 在您的開始環境中建立並參與旅程。 [此處提供更多資訊](https://docs.adobe.com/content/help/zh-Hant/journeys/using/building-journeys/about-journey-building/journey.html)
1. 檢查歷程版本是否沒有錯誤。 [此處提供更多資訊](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/testing-the-journey.html)
1. 呼叫 **/清單／歷程** API以擷取您最新歷程版本的UID歷程和UID。 如有需要，您可以呼叫 **/reyernies/`{uid}`/latest** ，以尋找您最新歷程版本的UID。
1. 使用您 **的開始環境參數** （orgID和sandboxName）呼叫匯出API。
1. 開啟傳回的裝載，然後檢查下列項目：
   * 如果您的匯出歷程包 **含特定憑證**，您需要將這些憑證取代為對應新環境的憑證。
   * 如果導出的歷程包 **含指向** XDM架構的事件 ****，則需要手動更新模式ID參考（如果ID值不同），該參考使用xdmEntity節點中新環境的模式ID。 此更新必須針對每個事件進行。 [此處提供更多資訊](https://docs.adobe.com/content/help/en/journeys/using/events-journeys/experience-event-schema.html)
   * 如果您的歷程包含電子郵件、簡訊或推播動作，如果目標環境中的名稱與開始環境中的名稱不同，您可能必須更新範本名稱或mobileApp名稱。
1. 使用您 **的目標環境** ，呼叫匯入API。 請注意，您可以視需要多次呼叫匯入API。 每次呼叫匯入API時，都會產生UUID和歷程中每個節點的名稱。
1. 匯入「歷程」後，您就可以在新的沙盒或環境中發佈它。


## 驗證

### 設定 API 存取

Journey Orchestration API存取是透過下列步驟設定。 這些步驟在 [Adobe I/O檔案中都有詳細說明](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)。

>[!CAUTION]
>
>若要在Adobe I/O中管理憑證，請確定您在「管理控制台」中擁有 <b>組織或開發人員</b> 帳戶的系統管 [理員權限](https://helpx.adobe.com/enterprise/using/manage-developers.html) 。

1. **檢查您是否有數位憑證**，或視需要建立憑證。 在下列步驟中，需要隨憑證提供的公開金鑰和私密金鑰。
1. **在Adobe I/O中建立[!DNL Journey Orchestration]Service** 的新整合併加以設定。 Journey Orchestration和Adobe Experience Platform需要產品設定檔存取。 然後會產生您的認證（API金鑰、用戶端密碼……）。
1. **從先前產生的認證建立JSON Web Token(JWT)** ，並使用您的私密金鑰簽名。 JWT會對Adobe驗證您的身分並授與您API存取權所需的所有身分與安全資訊進行編碼。 本節將詳述此步 [驟](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **透過POST要求或透過Developer Console介面** ，將您的JWT交換為存取Token。 此存取Token必須用於API請求的每個標題中。

若要建立安全的服務對服務Adobe I/O API作業階段，對Adobe服務的每個要求都必須在「授權」標題中包含下列資訊。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>**:這是您的個人組織ID,Adobe會針對每個例項提供一個組織ID:

   * &lt;ORGANIZATION> :您的生產實例
   若要取得您的組織ID值，請洽詢您的管理員或Adobe技術聯絡人。 建立新整合時，您也可以在授權清單(請參閱 [Adobe I/O檔案](https://www.adobe.io/authentication.html))中擷取它至Adobe I/O。

* **&lt;ACCESS_TOKEN>**:透過POST請求交換JWT時擷取的個人存取Token。

* **&lt;API_KEY>**:您的個人API金鑰。 在建立與服務的新整合後，Adobe I/O中就提供此 [!DNL Journey Orchestration] 功能。



## 匯出匯入API說明

此API可讓您依其uid匯出歷程版本及所有相關物件（歷程、事件、資料來源、欄位群組、自訂動作）。
產生的裝載可用來匯入其他環境（沙盒或例項）中的歷程版本。

| 方法 | 路徑 | 說明 |
|---|---|---|
| `[POST]` | /journeyVersions/import | 匯入由歷程版本匯出產生的歷程版本內容 |
| `[GET]` | /journeyVersions/`{uid}`/export | 匯出歷程版本 |
| `[GET]` | /journeys/`{uid}`latest | 取得最新的歷程版本 |
| `[POST]` | /list/journeys | 列出歷程的中繼資料及其歷程版本 |


### 出口特徵和護欄

* 不導出憑據，並插入佔位符（即INSERT_SECRET_HERE）。
在導出裝載後，必須手動插入新憑據（對應於目標環境），然後才能在目標環境中導入裝載。

* 當資料來源包含 **builtIn:true**，您不需要取代&quot;INSERT_SECRET_HERE&quot;。 這是由歷程環境自動管理的系統資料來源。

* 將導出以下對象，但這些對象不會在目標環境中導入：
   * **資料提供者**: acsDataProvider和acppsDataProvider
   * **欄位群組**:acppsFieldGroup
   * **自訂動作**:acsAction

* 出口前，此歷程必須有效。

### 匯入特性

* 在匯入期間，使用新的UUID和新名稱來建立歷程物件，以確保目標環境（例項或沙盒）中的唯一性。

* 如果匯入裝載包含機密預留位置，則會擲回錯誤。 您必須在開機自檢呼叫前替換憑證資訊以導入歷程。

## 警告與錯誤

可能的錯誤有：

* 在匯 **出時**，如果歷程版本無效：錯誤500

* 在匯 **入時**，如果裝載在修改後無效，或者在裝載中未正確定義憑證：錯誤400

* 在匯入步驟後，如果您嘗試在目標環境中發佈歷程，而未變更事件的XDM架構ID，則會出現錯誤。

