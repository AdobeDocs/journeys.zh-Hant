---
product: adobe campaign
title: 開始使用歷程API
description: 深入了解歷程API
products: journeys
feature: Journeys
role: User
level: Intermediate
source-git-commit: fa493cf1e856378e4d79a6932c30cebf5e11e028
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 2%

---

# 開始使用歷程API

## 關於限定和限制API

設定資料來源或動作時，您需建立與系統的連線，以擷取要用於歷程的其他資訊，或傳送訊息或API呼叫。

Journeys API每秒可支援最多5000個事件，但某些外部系統或API的輸送量可能不相等。 要防止超出這些系統，可以使用 **限定** 和 **節流** 限制每秒傳送事件數的API。

每次由歷程執行API呼叫時，都會通過API引擎。 如果達到API中設定的限制，若您使用上限設定API，則會拒絕呼叫，或將佇列最多6小時，並在您使用限制API時，按照收到的順序盡快處理。

例如，假設您已為外部系統定義每秒100次呼叫的上限或限制規則。 10個不同歷程中的自訂動作會呼叫您的系統。 如果一個歷程每秒收到200個呼叫，則會使用100個可用槽，並捨棄或將剩餘的100個槽加入佇列。 由於超出最大速率，其他9個歷程將沒有任何槽。 此粒度有助於保護外部系統免受過載和崩潰的影響。

>[!IMPORTANT]
>
>**限定規則** 是針對特定端點（稱為的URL），在沙箱層級設定，但會全域覆寫至該沙箱的所有歷程。
>
>**限制規則** 僅在生產沙箱上設定，適用於特定端點，但會針對所有沙箱的所有歷程進行全域設定。 每個組織只能有一個限制配置。

如需如何使用這些API的詳細資訊，請參閱下列章節：

* [設定API上限](capping.md)
* [限制API](throttling.md)

這兩個API也會在可用的Swagger檔案中說明 [此處](https://adobedocs.github.io/JourneyAPI/docs/).

## 資料來源和自訂動作容量 {#capacity}

針對 **外部資料來源**，每秒的呼叫數上限為15。 如果超過此限制，系統會根據使用中的API捨棄或排入佇列的其他呼叫。 您可以聯絡Adobe將端點納入允許清單，以提高私人外部資料來源的此限制，但此選項不適用於公開外部資料來源。 * [了解如何設定資料來源](../datasource/about-data-sources.md).

>[!NOTE]
>
>如果資料源使用的自定義身份驗證與用於資料源的終結點不同，則需要與Adobe聯繫，以將該終結點包含在允許清單中。

針對 **自訂動作**，您需要評估外部API的容量。 例如，如果Journey Optimizer每秒傳送1000次呼叫，而您的系統每秒只支援100次呼叫，則您需要定義上限或流量設定，以使系統不會飽和。 [了解如何設定動作](../action/action.md)

## 設定 API 存取 {#api}

若要將這些API與 [!DNL Journey Orchestration] 例項，您需要使用AdobeI/O主控台。 [!DNL Journey Orchestration] API存取權限是透過下列步驟設定。 以下各步驟在 [Adobe I/O檔案](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>若要在Adobe I/O中管理憑證，請確定您 <b>系統管理員</b> 組織或 [開發人員帳戶](https://helpx.adobe.com/enterprise/using/manage-developers.html) （在Admin Console中）。

1. **確認您擁有數位憑證**，或視需要建立。 下列步驟需要憑證隨附的公開金鑰和私密金鑰。
1. **建立新整合以 [!DNL Journey Orchestration] 服務** Adobe I/O並加以設定。 需要產品設定檔存取權 [!DNL Journey Orchestration] 和Adobe Experience Platform。 接著會產生您的認證（API金鑰、用戶端密碼……）。
1. **建立JSON網頁代號(JWT)** 從先前產生的憑證，並使用您的私密金鑰簽署。 JWT會對Adobe驗證身分並授予您API存取權所需的所有身分和安全資訊進行編碼。 此步驟在此中詳細說明 [節](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **將JWT交換為存取權杖** 透過POST要求或開發人員控制台介面。 此存取權杖必須用於API請求的每個標題中。

若要建立安全的服務對服務Adobe I/OAPI工作階段，對Adobe服務的每個要求都必須在授權標題中包含下列資訊。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**:這是您的個人組織ID，由Adobe為每個執行個體提供一個組織ID。 若要取得組織ID值，請洽詢您的管理員或Adobe技術聯絡人。 建立新整合時，您也可以將其擷取至Adobe I/O中，位於授權清單中(請參閱 <a href="https://www.adobe.io/authentication.html">Adobe I/O檔案</a>)。

* **&lt;access_token>**:您的個人存取權杖，此權杖是透過POST要求交換JWT時擷取的。

* **&lt;api_key>**:您的個人API金鑰。 它會在建立與 [!DNL Journey Orchestration] 服務。
