---
product: adobe campaign
title: 開始使用歷程 API
description: 深入了解歷程 API
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: a5dd3d23-c820-4ab7-bc6c-b1dcfe15022c
source-git-commit: 87d5cf223d9adec27eabcb55f2e09aa6d40b23a6
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 87%

---

# 開始使用歷程 API

## 關於設定上限與節流 API

當設定資料來源或動作時，您需建立與系統的連線，以擷取要用於歷程的其他資訊，或傳送訊息或 API 呼叫。

歷程 API 每秒最多支援 5000 個事件，但某些外部系統或 API 可能沒有等效的輸送量。若要防止這些系統過載，可以使用&#x200B;**設定上限**&#x200B;及&#x200B;**節流** API 來限制每秒傳送的事件數。

歷程每次執行 API 呼叫時，都會透過 API 引擎。如果達到 API 設定的限制，如果您使用的是設定 API 上限，則會拒絕呼叫，或者如果您使用的是節流 API，則呼叫最多佇列 6 小時並按照收到的順序盡快處理。

例如，假設您已為外部系統定義每秒100次呼叫的上限或節流規則。 10 個不同歷程的自訂動作會呼叫您的系統。 如果一個歷程每秒收到 200 個呼叫，則將使用 100 個可用插槽，並捨棄或將剩餘的 100 個插槽加入佇列。由於已超過最大速率，其他 9 個歷程將沒有任何插槽。 此詳細程度有助於保護外部系統免於過載及損毀。

>[!IMPORTANT]
>
>**設定上限規則**&#x200B;在沙箱層級針對特定端點 (呼叫的 URL) 進行設定，但會針對該沙箱的所有歷程進行全域設定。
>
>**節流規則**&#x200B;僅在生產沙箱針對特定端點進行設定，但會針對所有沙箱的所有歷程進行全域設定。 每個組織只能有一個節流設定。

深入了解如何使用這些 API，請參閱下列章節：

* [設定 API 上限](capping.md)
* [節流 API](throttling.md)

[此處](https://adobedocs.github.io/JourneyAPI/docs/)的 Swagger 檔案也描述了這兩個 API。

## 資料來源和自訂動作容量 {#capacity}

對於&#x200B;**外部資料來源**，每秒的呼叫數上限為 15。 如果超過此限制，系統會根據正在使用的 API 將其他呼叫捨棄或排入佇列。可以透過聯絡 Adobe 將端點加入允許清單，以提高這項針對私人外部資料來源的限制，但此選項不適用於公開外部資料來源。* [了解如何設定資料來源](../datasource/about-data-sources.md)。

>[!NOTE]
>
>如果資料來源使用的自訂驗證與用於資料來源的端點不同，則需聯絡 Adobe，以將該端點加入允許清單。

對於&#x200B;**自訂動作**，您需要評估外部 API 的容量。 例如，如果 Journey Optimizer 每秒傳送 1000 次呼叫，而您的系統每秒只支援 100 次呼叫，則您需要定義上限或節流設定，以使系統不會飽和。[了解如何設定動作](../action/action.md)

## 設定 API 存取 {#api}

若要將這些 API 與您的[!DNL Journey Orchestration]執行個體一起使用，您需要利用 AdobeI/O 主控台。[!DNL Journey Orchestration] API 存取權限是透過下列步驟設定。[Adobe I/O 文件](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)詳細介紹了這些步驟。

>[!CAUTION]
>
>若要在 Adobe I/O 管理憑證，請確認您在組織擁有<b>系統管理員</b>權限或在 Admin Console 擁有[開發人員帳戶](https://helpx.adobe.com/jp/enterprise/using/manage-developers.html)。

1. **請確認您擁有數位憑證**，或視需要建立。 下列步驟需要憑證隨附的公開金鑰與私人金鑰。
1. 在 Adobe I/O **建立新整合以[!DNL Journey Orchestration]服務**&#x200B;並加以設定。 [!DNL Journey Orchestration]和 Adobe Experience Platform 需要產品設定檔存取權。然後，將產生您的憑證 (API 金鑰、用戶端密碼……)。

>[!CAUTION]
>
>不建議使用產生存取權杖的JWT方法。 所有新的整合必須使用 [OAuth伺服器對伺服器驗證方法](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html#select-oauth-server-to-server). Adobe也建議您將現有的整合移轉至OAuth方法。
>
>閱讀下列重要檔案：
>[應用程式從JWT移轉至OAuth的移轉指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)，
>[使用OAuth的新舊應用程式實作指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)，
>[使用OAuth伺服器對伺服器憑證方法的優勢](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/#why-oauth-server-to-server-credentials)

若要建立安全的服務對服務 Adobe I/O API 工作階段，對 Adobe 服務的每個請求都必須在授權標題中包含下列資訊。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>**：這是您的個人組織 ID，Adobe 為每個執行個體提供一個組織 ID。 若要取得組織 ID 值，請洽詢您的管理員或 Adobe 技術聯絡人。 在授權清單中建立新整合時，您也可以將其擷取至 Adobe I/O (請參閱 [Adobe I/O 文件](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md))。

* **&lt;access_token>**：您的個人存取權杖

* **&lt;API_KEY>**：您的個人 API 金鑰。 在建立與[!DNL Journey Orchestration]服務的新整合後，它會在 Adobe I/O 中提供。
