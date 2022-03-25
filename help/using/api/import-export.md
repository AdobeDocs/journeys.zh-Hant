---
product: adobe campaign
title: 導入導出API說明
description: 瞭解有關導入導出API的詳細資訊。
products: journeys
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '1123'
ht-degree: 1%

---


# 使用導出 — 導入API

使用單個API調用導出行程版本及其所有相關對象（行程、事件、資料源、欄位組、自定義操作）。 導出產生的負載可用於輕鬆地將行程導入到其他環境（實例或沙盒）中。
此功能允許您管理跨多個實例或多個test環境工作流的行程。


## 資源

Journey Orchestration導出 — 導入API在可用的Swagger檔案中描述 [這裡](https://adobedocs.github.io/JourneyAPI/docs/)。

要將此API與Journey Orchestration實例一起使用，您需要使用AdobeI/O控制台。 您可以按照此操作 [Adobe開發人員控制台入門](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) 然後使用此頁中的部分。

要test和準備您的整合，可提供Postman收藏 [這裡](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json)。


## 導出 — 導入流

我們建議按照以下步驟在不同環境之間導出和導入您的行程：

1. 在起始環境中建立行程並為其參數化。 [此處提供更多資訊](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/about-journey-building/journey.html)
1. 檢查行程版本是否沒有錯誤。 [此處提供更多資訊](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/testing-the-journey.html)
1. 呼叫 **/list/rougers** API，用於檢索您的最新行程版本的UID行程和UID。 如果需要，你可以打電話 **/reymers/`{uid}`/最新** 以查找您的最新旅程版本的UID。
1. 呼叫 **出口** 具有啟動環境參數（orgID和sandboxName）的API。
1. 開啟返回負載，然後檢查以下項：
   * 如果導出的行程包含 **特定憑據**，您需要將這些憑據替換為與新環境對應的憑據。
   * 如果導出的行程包含 **事件** 這表明 **XDM架構**，如果ID值不同，則需要手動更新使用xdmEntity節點中新環境的架構ID的架構ID引用。 需要對每個事件執行此更新。 [此處提供更多資訊](https://experienceleague.adobe.com/docs/journeys/using/events-journeys/experience-event-schema.html)
   * 如果您的旅程包含電子郵件、簡訊或推送操作，則如果目標環境中的名稱與起始環境中的名稱不同，則可能必須更新模板名稱或mobileApp名稱。
1. 呼叫 **導入** 具有目標環境參數（orgID和sandboxName）的API。 請注意，您可以根據需要多次調用導入API。 每次調用導入API時，都會生成UUID和旅程中包含的每個對象的名稱。
1. 導入Journey後，您可以在Journey Orchestration應用程式中發佈它。 詳細資訊 [這裡](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/publishing-the-journey.html)


## 驗證

### 設定 API 存取

Journey OrchestrationAPI訪問通過以下步驟設定。 以下每個步驟均在 [Adobe I/O文檔](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)。

>[!CAUTION]
>
>要在Adobe I/O中管理證書，請確保 <b>系統管理員</b> 組織或 [開發者帳戶](https://helpx.adobe.com/tw/enterprise/using/manage-developers.html) 在管理控制台中。

1. **檢查您有數字證書**，或根據需要建立。 在以下步驟中需要隨證書提供的公鑰和私鑰。
1. **建立新整合到 [!DNL Journey Orchestration] 服務** Adobe I/O並配置。 Journey Orchestration和Adobe Experience Platform需要產品配置檔案訪問。 然後將生成您的憑據（API密鑰、客戶端密鑰……）。
1. **建立JSON Web令牌(JWT)** 從先前生成的憑據中，使用您的私鑰進行簽名。 JWT對Adobe驗證身份和授予您訪問API的權限所需的所有身份和安全資訊進行編碼。 此步驟在本中詳細介紹 [節](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **將JWT交換為訪問令牌** 通過POST請求或通過開發人員控制台介面。 此訪問令牌必須用於API請求的每個標頭。

要建立安全的服務到服務Adobe I/OAPI會話，對Adobe服務的每個請求都必須在「授權」標頭中包含以下資訊。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**:這是您的個人組織ID,Adobe為每個實例提供一個組織ID:

   * &lt;organization> :您的生產實例
   要獲取您的組織ID值，請咨詢您的管理員或Adobe技術聯繫人。 建立新整合時，您還可以在許可證清單中將其檢索到Adobe I/O(請參見 [Adobe I/O文檔](https://www.adobe.io/authentication.html))。

* **&lt;access_token>**:通過POST請求交換JWT時檢索的個人訪問令牌。

* **&lt;api_key>**:您的個人API密鑰。 在建立新整合後在Adobe I/O中提供 [!DNL Journey Orchestration] 服務。



## 導出 — 導入API說明

此API允許您導出由其UID標識的行程版本，以及由其uid標識的所有相關對象（行程、事件、資料源、欄位組、自定義操作）。
生成的負載可用於在另一個環境（沙盒或實例）中導入行程版本。

| 方法 | 路徑 | 說明 |
|---|---|---|
| `[POST]` | /journeyVersions/import | 導入由行程版本導出生成的行程版本內容 |
| `[GET]` | /journey版本/`{uid}`/導出 | 導出行程版本 |
| `[GET]` | /reymers/`{uid}`/最新 | 獲取最新的旅程版本 |
| `[POST]` | /list/rougers | 列出旅程的元資料及其旅程版本 |


### 導出特性和護欄

* 導出前，該行程必須有效。

* 不導出憑據，並在響應負載中插入佔位符（即INSERT_SECRET_HERE）。
在導出調用後，必須手動插入新憑據（對應於目標環境），然後才能在目標環境中導入負載。

* 將導出以下對象，但不會在目標環境中導入它們。 這些是由Journey Orchestration自動管理的系統資源。 您不需要替換「INSERT_SECRET_HERE」。
   * **資料提供程式**:&quot;Adobe Campaign Standard資料提供程式&quot;(acsDataProvider)和&quot;Experience Platform&quot;(acppsDataProvider)
   * **欄位組** （資料實體）:&quot;ProfileFieldGroup&quot;(acppsDataPack)



### 導入特性

* 在導入過程中，使用新的UID和新名稱建立行程對象，以確保目標環境（實例或沙盒）中的唯一性。

* 如果導入負載包含秘密佔位符，則會引發錯誤。 在POST呼叫導入行程之前，必須替換憑據資訊。

## 警告和錯誤

潛在錯誤有：

* 在 **導出時間**，如果行程版本無效：錯誤500

* 在 **導入時間**，如果負載在修改後無效，或者在負載中未正確定義憑據：錯誤400

* 在導入步驟後，如果目標環境中事件的XDM架構ID無效，則Journey Orchestration應用程式中會出現錯誤。 在這種情況下，將不可能公佈這段旅程。