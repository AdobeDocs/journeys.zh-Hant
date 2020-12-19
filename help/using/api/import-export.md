---
product: adobe campaign
solution: Journey Orchestration
title: 匯入匯出API說明
description: 進一步瞭解匯入匯出API。
products: journeys
translation-type: tm+mt
source-git-commit: 8da1d4a6c01279bf502c3ec39bdaba8fcc8e64f8
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 2%

---


# 使用Export-Import API

使用單一API呼叫匯出歷程版本及其所有相關物件（歷程、事件、資料來源、欄位群組、自訂動作）。 匯出產生的裝載可用來輕鬆將歷程匯入其他環境（例項或沙盒）。
此功能可讓您管理多個執行個體或多個測試環境工作流程的歷程。


## 資源

Journey Orchestration Export-Import API是在[此處](https://adobedocs.github.io/JourneyAPI/docs/)的Swagger檔案中描述的。

若要將此API與您的Journey Orchestration例項搭配使用，您必須使用AdobeI/O Console。 您可以從以下[開始使用Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md)，然後使用本頁中的章節。

若要測試並準備整合，[此處](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json)提供Postman系列。


## 匯出——匯入流程

我們建議您依照下列步驟，跨環境匯出和匯入您的旅程：

1. 在您的開始環境中建立並參與旅程。 [此處提供更多資訊](https://docs.adobe.com/content/help/zh-Hant/journeys/using/building-journeys/about-journey-building/journey.html)
1. 檢查歷程版本是否沒有錯誤。 [此處提供更多資訊](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/testing-the-journey.html)
1. 呼叫&#x200B;**/list/royernys** API以擷取您最新歷程版本的UID歷程和UID。 如有需要，您可以呼叫&#x200B;**/journeys/`{uid}`/latest**，以尋找您最新歷程版本的UID。
1. 使用您的開始環境參數（orgID和sandboxName）呼叫&#x200B;**export** API。
1. 開啟傳回的裝載，然後檢查下列項目：
   * 如果導出的歷程包含&#x200B;**特定憑據**，則需要將這些憑據替換為與新環境對應的憑據。
   * 如果導出的旅程包含指向&#x200B;**XDM架構**&#x200B;的&#x200B;**events**，則需要手動更新架構ID參考（如果ID值不同），該參考使用xdmEntity節點中新環境的架構ID。 此更新必須針對每個事件進行。 [此處提供更多資訊](https://docs.adobe.com/content/help/en/journeys/using/events-journeys/experience-event-schema.html)
   * 如果您的歷程包含電子郵件、簡訊或推播動作，如果目標環境中的名稱與開始環境中的名稱不同，您可能必須更新範本名稱或mobileApp名稱。
1. 使用您的目標環境參數（orgID和sandboxName）呼叫&#x200B;**Import** API。 請注意，您可以視需要多次呼叫匯入API。 每次呼叫匯入API時，都會產生UUID和歷程中每個物件的名稱。
1. 匯入Journey後，您就可以在Journey Orchestration應用程式中發佈它。 更多資訊[這裡](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/publishing-the-journey.html)


## 驗證

### 設定 API 存取

Journey Orchestration API存取是透過下列步驟設定。 這些步驟均在[Adobe I/O檔案](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)中詳細說明。

>[!CAUTION]
>
>若要在Adobe I/O中管理憑證，請確定您在組織中擁有<b>系統管理員</b>權限，或在管理控制台中擁有[開發人員帳戶](https://helpx.adobe.com/enterprise/using/manage-developers.html)。

1. **檢查您是否有數位憑證**，或視需要建立憑證。在下列步驟中，需要隨憑證提供的公開金鑰和私密金鑰。
1. **在Adobe I/O中建立 [!DNL Journey Orchestration]** Services的新整合併加以設定。Journey Orchestration和Adobe Experience Platform需要產品設定檔存取。 然後會產生您的認證（API金鑰、用戶端密碼……）。
1. **從先前產生的認證建立JSON網** 頁Token(JWT)，並使用您的私密金鑰簽名。JWT會對Adobe驗證您的身分並授與您API存取權所需的所有身分與安全資訊進行編碼。 此步驟在[部分](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)中有詳細說明
1. **透過POST要求或透過「開發人** 員控制台介面」，將您的JWT交換為存取Token。此存取Token必須用於API請求的每個標題中。

若要建立安全的服務對服務Adobe I/O API作業階段，對Adobe服務的每個要求都必須在「授權」標題中包含下列資訊。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**:這是您的個人組織ID,Adobe會針對每個例項提供一個組織ID:

   * &lt;organization> :您的生產實例
   若要取得您的組織ID值，請洽詢您的管理員或Adobe技術聯絡人。 建立新整合時，您也可以在授權清單中擷取它至Adobe I/O（請參閱[Adobe I/O檔案](https://www.adobe.io/authentication.html)）。

* **&lt;access_token>**:透過POST請求交換JWT時擷取的個人存取Token。

* **&lt;api_key>**:您的個人API金鑰。在建立與[!DNL Journey Orchestration]服務的新整合後，Adobe I/O中就提供了它。



## 匯出匯入API說明

此API可讓您匯出由其UID識別的歷程版本，以及所有相關物件（歷程、事件、資料來源、欄位群組、自訂動作）（依其uid）。
產生的裝載可用來匯入其他環境（沙盒或例項）中的歷程版本。

| 方法 | 路徑 | 說明 |
|---|---|---|
| `[POST]` | /journeyVersions/import | 匯入由歷程版本匯出產生的歷程版本內容 |
| `[GET]` | /journeyVersions/`{uid}`/export | 匯出歷程版本 |
| `[GET]` | /journeys/`{uid}`/latest | 取得最新的歷程版本 |
| `[POST]` | /list/journeys | 列出歷程的中繼資料及其歷程版本 |


### 出口特徵和護欄

* 出口前，此歷程必須有效。

* 憑證不會匯出，而會在回應裝載中插入預留位置（即INSERT_SECRET_HERE）。
在匯出呼叫後，您必須先手動插入新憑證（對應於目標環境），才能將裝載匯入目標環境。

* 以下對象將導出，但不會在目標環境中導入。 這些是由Journey Orchestration自動管理的系統資源。 您不需要取代「INSERT_SECRET_HERE」。
   * **資料提供者**:「Adobe Campaign標準資料提供者」(acsDataProvider)和「體驗平台」(acppsDataProvider)
   * **欄位群組** (dataEntities):&quot;ProfileFieldGroup&quot;(acppsDataPack)



### 匯入特性

* 在匯入期間，使用新的UID和新名稱來建立歷程物件，以確保目標環境（例項或沙盒）中的唯一性。

* 如果匯入裝載包含機密預留位置，則會擲回錯誤。 您必須在開機自檢呼叫前替換憑證資訊以導入歷程。

## 警告與錯誤

可能的錯誤有：

* 在&#x200B;**匯出時間**，如果歷程版本無效：錯誤500

* 在&#x200B;**讀入時間**，如果裝載在修改後無效，或者認證在裝載中未定義：錯誤400

* 匯入步驟後，如果您事件的XDM架構ID在目標環境中無效，則「歷程協調」應用程式中會出現錯誤。 在這種情況下，將無法公佈這段歷程。