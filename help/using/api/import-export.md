---
product: adobe campaign
title: 匯入匯出API說明
description: 深入了解匯入匯出API。
products: journeys
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '1123'
ht-degree: 1%

---


# 使用匯出匯入API

使用單一API呼叫，匯出歷程版本及其所有相關物件（歷程、事件、資料來源、欄位群組、自訂動作）。 匯出產生的裝載可用來輕鬆將歷程匯入至其他環境（例項或沙箱）。
此功能可讓您管理跨多個執行個體或多個測試環境工作流程的歷程。


## 資源

Journey Orchestration匯出 — 匯入API在[此處](https://adobedocs.github.io/JourneyAPI/docs/)可用的Swagger檔案中說明。

若要將此API與您的Journey Orchestration例項搭配使用，您需要使用AdobeI/O主控台。 您可以依照此[Adobe開發人員控制台快速入門](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md)開始，然後使用本頁面中的各節。

若要測試並準備您的整合，可在[此處](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json)取得Postman集合。


## 匯出匯入流程

建議您依照下列步驟，匯出和匯入您在不同環境中的歷程：

1. 在您的開始環境中建立歷程並為其參數。 [更多資訊，請前往](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/about-journey-building/journey.html)
1. 檢查歷程版本是否沒有錯誤。 [更多資訊，請前往](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/testing-the-journey.html)
1. 呼叫&#x200B;**/list/journeys** API以擷取您最新歷程版本的UID歷程及UID。 如有需要，您可以呼叫&#x200B;**/journeys/`{uid}`/latest**&#x200B;以尋找您最新歷程版本的UID。
1. 使用您的開始環境參數（orgID和sandboxName）呼叫&#x200B;**export** API。
1. 開啟傳回的裝載，然後檢查下列項目：
   * 如果您的匯出歷程包含&#x200B;**特定憑證**，則需要將這些憑證取代為與新環境對應的憑證。
   * 如果您匯出的歷程包含&#x200B;**events**，而該事件指向&#x200B;**XDM架構**，則如果ID值不同，則需要以xdmEntity節點中新環境的架構ID手動更新架構ID參考。 必須針對每個事件完成此更新。 [更多資訊，請前往](https://experienceleague.adobe.com/docs/journeys/using/events-journeys/experience-event-schema.html)
   * 如果您的歷程包含電子郵件、簡訊或推播動作，如果目標環境中的名稱與啟動環境中的名稱不同，則您可能必須更新範本名稱或mobileApp名稱。
1. 使用您的目標環境參數（orgID和sandboxName）呼叫&#x200B;**Import** API。 請注意，您可以視需要多次呼叫匯入API。 每次呼叫匯入API時，歷程中所包含的每個物件名稱都會產生。
1. 匯入歷程後，您就可以在Journey Orchestration應用程式中發佈它。 更多資訊[此處](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/publishing-the-journey.html)


## 驗證

### 設定 API 存取

Journey OrchestrationAPI存取權是透過下列步驟設定。 在[Adobe I/O檔案](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)中會詳細說明這些步驟。

>[!CAUTION]
>
>若要在Adobe I/O中管理憑證，請確定您在組織上擁有<b>系統管理員</b>權限，或在管理控制台中擁有[開發人員帳戶](https://helpx.adobe.com/enterprise/using/manage-developers.html)權限。

1. **檢查您是否擁有數位憑證**，或視需要建立憑證。下列步驟需要憑證隨附的公開金鑰和私密金鑰。
1. **建立ServiceinAdobe I/O的 [!DNL Journey Orchestration]** 新整合併加以設定。Journey Orchestration和Adobe Experience Platform需要產品設定檔存取權。 接著會產生您的認證（API金鑰、用戶端密碼……）。
1. **從先前產生的憑證建立JSON網頁代號(JWT)** ，並使用您的私密金鑰簽署。JWT會對Adobe驗證身分並授予您API存取權所需的所有身分和安全資訊進行編碼。 此步驟在此[節](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)中詳細說明
1. **透過POST要求或** 開發人員控制台介面，將JWT交換為存取代號。此存取權杖必須用於API請求的每個標題中。

若要建立安全的服務對服務Adobe I/OAPI工作階段，對Adobe服務的每個要求都必須在授權標題中包含下列資訊。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**:這是您的個人組織ID，由Adobe為每個執行個體提供一個組織ID:

   * &lt;organization> :您的生產執行個體
   若要取得組織ID值，請洽詢您的管理員或Adobe技術聯絡人。 建立新整合時，您也可以在授權清單中將其擷取至Adobe I/O(請參閱[Adobe I/O檔案](https://www.adobe.io/authentication.html))。

* **&lt;access_token>**:您的個人存取權杖，此權杖是透過POST要求交換JWT時擷取的。

* **&lt;api_key>**:您的個人API金鑰。它會在建立[!DNL Journey Orchestration]服務的新整合後以Adobe I/O提供。



## 匯出匯入API說明

此API可讓您匯出以其UID識別的歷程版本，以及以其uid匯出所有相關物件（歷程、事件、資料來源、欄位群組、自訂動作）。
產生的裝載可用來匯入其他環境（沙箱或例項）中的歷程版本。

| 方法 | 路徑 | 說明 |
|---|---|---|
| `[POST]` | /journeyVersions/import | 匯入從歷程版本匯出產生的歷程版本內容 |
| `[GET]` | /journeyVersions/`{uid}`/export | 匯出歷程版本 |
| `[GET]` | /journeys/`{uid}`/latest | 取得歷程的最新歷程版本 |
| `[POST]` | /list/journeys | 列出歷程及其歷程版本的中繼資料 |


### 導出特性和護欄

* 匯出前，歷程必須有效。

* 憑證不會匯出，且預留位置（即INSERT_SECRET_HERE）會插入回應裝載中。
匯出呼叫後，您必須先手動插入新憑證（與目標環境對應），才能在目標環境中匯入裝載。

* 將導出以下對象，但這些對象永遠不會在目標環境中導入。 這些是由Journey Orchestration自動管理的系統資源。 您不需要取代「INSERT_SECRET_HERE」。
   * **資料提供者**:&quot;Adobe Campaign Standard Data Provider&quot;(acsDataProvider)和&quot;Experience Platform&quot;(acppsDataProvider)
   * **欄位群組** (dataEntities):&quot;ProfileFieldGroup&quot;(acppsDataPack)



### 匯入特徵

* 在匯入期間，歷程物件會以新UID和新名稱建立，以確保目標環境（例項或沙箱）中的唯一性。

* 如果匯入裝載包含機密預留位置，則會擲回錯誤。 您必須在POST呼叫前取代憑證資訊，才能匯入歷程。

## 警告和錯誤

潛在錯誤為：

* 在&#x200B;**匯出時間**，如果歷程版本無效：錯誤500

* 在&#x200B;**匯入時間**，如果修改後有效負載無效，或有效負載中未妥善定義憑證：錯誤400

* 在匯入步驟後，如果目標環境中事件的XDM結構ID無效，Journey Orchestration應用程式中就會顯示錯誤。 在此情況下，將無法發佈歷程。