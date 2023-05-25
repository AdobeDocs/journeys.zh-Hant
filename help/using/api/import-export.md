---
product: adobe campaign
title: 匯入匯出API說明
description: 進一步瞭解匯入匯出API。
products: journeys
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '1123'
ht-degree: 27%

---


# 使用匯出 — 匯入API

使用單一API呼叫匯出歷程版本及其所有相關物件（歷程、事件、資料來源、欄位群組、自訂動作）。 匯出產生的裝載可用於輕鬆將歷程匯入另一個環境（例項或沙箱）。
此功能可讓您跨多個執行個體或多個測試環境工作流程管理您的歷程。


## 資源

可用的Swagger檔案中說明Journey Orchestration匯出 — 匯入API [此處](https://adobedocs.github.io/JourneyAPI/docs/).

若要搭配Journey Orchestration執行個體使用此API，您需要使用AdobeI/O主控台。 您可以依照以下說明開始進行 [Adobe Developer Console快速入門](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) 然後使用此頁面中的區段。

若要測試並準備整合，可使用Postman集合 [此處](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json).


## 匯出匯入流程

我們建議遵循下列步驟，在不同環境中匯出和匯入您的歷程：

1. 在您的開始環境中建立歷程並設定其引數。 [更多資訊請前往此處](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/about-journey-building/journey.html)
1. 檢查歷程版本是否沒有錯誤。 [更多資訊請前往此處](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/testing-the-journey.html)
1. 呼叫 **/list/journeys** 用於擷取UID歷程和您最新歷程版本UID的API。 如有需要，您可以呼叫 **/journeys/`{uid}`/latest** 以尋找您最新歷程版本的UID。
1. 呼叫 **匯出** 包含啟動環境引數（orgID和sandboxName）的API。
1. 開啟傳回裝載，然後檢查下列專案：
   * 如果您的匯出歷程包含 **特定認證**，您需要將這些憑證替換為與新環境對應的憑證。
   * 如果您的匯出歷程包含 **事件** 該點指向 **XDM結構描述**，如果ID值不同，您需要在xdmEntity節點中手動使用新環境的方案ID更新方案ID參考。 每個事件都需要完成此更新。 [更多資訊請前往此處](https://experienceleague.adobe.com/docs/journeys/using/events-journeys/experience-event-schema.html)
   * 如果您的歷程包含電子郵件、簡訊或推播動作，如果目標環境中的名稱與開始環境中的名稱不同，您可能需要更新範本名稱或mobileApp名稱。
1. 呼叫 **匯入** API搭配您的目標環境引數（orgID和sandboxName）。 請注意，您可以視需要多次呼叫匯入API。 每次呼叫匯入API時，都會產生歷程中包含之每個物件的UUID和名稱。
1. 匯入歷程後，您可以在Journey Orchestration應用程式中發佈歷程。 更多資訊 [此處](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/publishing-the-journey.html)


## 驗證

### 設定 API 存取

Journey OrchestrationAPI存取可透過下列步驟設定。 [Adobe I/O 文件](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)詳細介紹了這些步驟。

>[!CAUTION]
>
>若要在 Adobe I/O 管理憑證，請確認您在組織擁有<b>系統管理員</b>權限或在 Admin Console 擁有[開發人員帳戶](https://helpx.adobe.com/jp/enterprise/using/manage-developers.html)。

1. **請確認您擁有數位憑證**，或視需要建立。 下列步驟需要憑證隨附的公開金鑰與私人金鑰。
1. 在 Adobe I/O **建立新整合以[!DNL Journey Orchestration]服務**&#x200B;並加以設定。 Journey Orchestration和Adobe Experience Platform需要產品設定檔存取權。 然後，將產生您的憑證 (API 金鑰、用戶端密碼……)。
1. 從之前產生的憑證&#x200B;**建立 JSON 網頁語彙基元 (JWT)**，並使用私人金鑰對其進行簽署。JWT 會對 Adobe 驗證身分並授予您存取 API 所需的所有身分與安全資訊進行編碼。 此步驟在此[章節](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)中有詳細說明
1. 透過 POST 要求或透過 Developer Console 介面&#x200B;**將 JWT 換成存取權杖**。必須在 API 請求的每個標題中使用此存取權杖。

若要建立安全的服務對服務 Adobe I/O API 工作階段，對 Adobe 服務的每個請求都必須在授權標題中包含下列資訊。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**：這是您的個人組織ID，Adobe會為每個執行個體提供一個組織ID：

   * &lt;organization> ：您的生產執行個體
   若要取得組織 ID 值，請洽詢您的管理員或 Adobe 技術聯絡人。 在授權清單中建立新整合時，您也可以將其擷取至 Adobe I/O (請參閱 [Adobe I/O 文件](https://www.adobe.io/authentication.html))。

* **&lt;ACCESS_TOKEN>**：您的個人存取權杖，此權杖是透過 POST 要求交換 JWT 時所擷取。

* **&lt;API_KEY>**：您的個人 API 金鑰。 在建立與[!DNL Journey Orchestration]服務的新整合後，它會在 Adobe I/O 中提供。



## Export-Import API說明

此API可讓您匯出以其UID識別的歷程版本，以及以其uid識別的所有相關物件（歷程、事件、資料來源、欄位群組、自訂動作）。
產生的裝載可用於匯入另一個環境（沙箱或執行個體）中的歷程版本。

| 方法 | 路徑 | 說明 |
|---|---|---|
| `[POST]` | /journeyVersions/import | 匯入由歷程版本匯出產生的歷程版本內容 |
| `[GET]` | /journeyVersions/`{uid}`/export | 匯出歷程版本 |
| `[GET]` | /journeys/`{uid}`/latest | 取得歷程的最新歷程版本 |
| `[POST]` | /list/journeys | 列出歷程的中繼資料及其歷程版本 |


### 匯出特徵和護欄

* 匯出前，歷程必須有效。

* 認證不會匯出，而預留位置（即INSERT_SECRET_HERE）會插入回應裝載中。
在匯出呼叫後，您必須手動插入新認證（與目標環境相對應），才能在目標環境中匯入裝載。

* 下列物件會匯出，但絕不會匯入目標環境中。 這些是由Journey Orchestration自動管理的系統資源。 您不需要取代「INSERT_SECRET_HERE」。
   * **DataProviders**：「Adobe Campaign Standard資料提供者」(acsDataProvider)和「Experience Platform」(acppsDataProvider)
   * **欄位群組** (dataEntities)： &quot;ProfileFieldGroup&quot; (acppsDataPack)



### 匯入特性

* 在匯入期間，歷程物件是以新UID和新名稱建立，以確保目標環境（執行個體或沙箱）中的唯一性。

* 如果匯入裝載包含密碼預留位置，則會擲回錯誤。 您必須在POST呼叫之前取代認證資訊才能匯入歷程。

## 警告和錯誤

可能的錯誤包括：

* 於 **匯出時間**，如果歷程版本無效：錯誤500

* 於 **匯入時間**，如果裝載修改後無效，或裝載中未妥善定義認證：錯誤400

* 匯入步驟後，如果事件的XDM結構描述ID在目標環境中無效，則Journey Orchestration應用程式中會出現錯誤。 在這種情況下，無法發佈歷程。