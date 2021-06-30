---
product: adobe campaign
title: 設定API說明上限
description: 進一步了解上限API。
products: journeys
feature: 歷程
role: Business Practitioner
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 1%

---

# 使用上限設定API

## 簡介

[!DNL Journey Orchestration]的API支援5000個事件/秒，但某些外部系統或API的吞吐量無法相等。這就是[!DNL Journey Orchestration]隨附一項名為「設定API上限」的專用功能的原因，該功能可監控並限制我們對外部系統的執行率。

在資料來源設定期間，您將定義系統連線，以擷取將用於歷程的其他資訊，或用於動作定義，您將設定協力廠商系統的連線，以傳送訊息或API呼叫。 每次由歷程執行API呼叫時，即會查詢限定API，呼叫就會透過API引擎。 如果已定義限制，則會拒絕呼叫，且外部系統不會超載。

要了解有關操作或資料源配置的詳細資訊，請參閱[關於操作](https://experienceleague.adobe.com/docs/journeys/using/action-journeys/action.html)或[關於資料源](https://experienceleague.adobe.com/docs/journeys/using/data-source-journeys/about-data-sources.html)


## 資源

>[!NOTE]
>
>[!DNL Journey Orchestration]限定API是在[此處](https://adobedocs.github.io/JourneyAPI/docs/)可用的Swagger檔案中說明。

若要將此API與您的[!DNL Journey Orchestration]例項搭配使用，您需要使用AdobeI/O主控台。 您可以依照此[Adobe開發人員控制台快速入門](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md)開始，然後使用本頁面中的各節。

若要測試並準備您的整合，可在[此處](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)取得Postman集合。

## 驗證

### 設定 API 存取

[!DNL Journey Orchestration] API存取權限是透過下列步驟設定。在[Adobe I/O檔案](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)中會詳細說明這些步驟。

>[!CAUTION]
>
>若要在Adobe I/O中管理憑證，請確定您在組織上擁有<b>系統管理員</b>權限，或在管理控制台中擁有[開發人員帳戶](https://helpx.adobe.com/enterprise/using/manage-developers.html)權限。

1. **檢查您是否擁有數位憑證**，或視需要建立憑證。下列步驟需要憑證隨附的公開金鑰和私密金鑰。
1. **建立ServiceinAdobe I/O的 [!DNL Journey Orchestration]** 新整合併加以設定。[!DNL Journey Orchestration]和Adobe Experience Platform需要產品設定檔存取權。 接著會產生您的認證（API金鑰、用戶端密碼……）。
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

   若要取得組織ID值，請洽詢您的管理員或Adobe技術聯絡人。 建立新整合時，您也可以在授權清單中將其擷取至Adobe I/O(請參閱<a href="https://www.adobe.io/authentication.html">Adobe I/O檔案</a>)。

* **&lt;access_token>**:您的個人存取權杖，此權杖是透過POST要求交換JWT時擷取的。

* **&lt;api_key>**:您的個人API金鑰。它會在建立[!DNL Journey Orchestration]服務的新整合後以Adobe I/O提供。



## 設定API說明上限

上限API可協助您建立、設定及監控上限設定。

| 方法 | 路徑 | 說明 |
|---|---|---|
| [!DNL POST] | list/endpointConfigs | 獲取端點限定配置清單 |
| [!DNL POST] | /endpointConfigs | 建立端點限定配置 |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | 部署端點限定配置 |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeploy | 取消部署端點限定配置 |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | 檢查是否可部署端點限定配置 |
| [!DNL PUT] | /endpointConfigs/`{uid}` | 更新端點限定配置 |
| [!DNL GET] | /endpointConfigs/`{uid}` | 擷取端點上限設定 |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | 刪除引入點限定配置 |

建立或更新設定時，會自動執行檢查，以保證有效負載的語法和完整性。
如果發生某些問題，操作會傳回警告或錯誤，以協助您修正設定。



## 端點設定

端點設定的基本結構如下：

```
{
    "url": "<endpoint URL>",  //wildcards are allowed in the endpoint URL
    "methods": [ "<HTTP method such as GET, POST, >, ...],
    "services": {
        "<service name>": { . //must be "action" or "dataSource" 
            "maxHttpConnections": <max connections count to the endpoint>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

### 範例:

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "maxHttpConnections": 30000,
      "rating": {
        "maxCallsCount": 5000,
        "periodInMs": 1000
      }
    }
  },
  "orgId": "<IMS Org Id>"
}
```


## 警告和錯誤

當呼叫&#x200B;**canDeploy**&#x200B;方法時，該進程將驗證配置並返回由其唯一ID標識的驗證狀態，其中一種方式為：

```
"ok" or "error"
```

潛在錯誤為：

* **ERR_ENDPOINTCONFIG_100**:限定配置：遺失或無效的url
* **ERR_ENDPOINTCONFIG_101**:限定配置：格式錯誤的url
* **ERR_ENDPOINTCONFIG_102**:限定配置：格式錯誤的url:主機中不允許在url中使用通配符
* **ERR_ENDPOINTCONFIG_103**:限定配置：缺少HTTP方法
* **ERR_ENDPOINTCONFIG_104**:限定配置：未定義呼叫評級
* **ERR_ENDPOINTCONFIG_107**:限定配置：最大呼叫計數無效(maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**:限定配置：最大呼叫計數無效(periodInMs)
* **ERR_ENDPOINTCONFIG_111**:限定配置：無法建立端點配置：有效負載
* **ERR_ENDPOINTCONFIG_112**:限定配置：無法建立端點配置：應為JSON裝載
* **ERR_AUTHORING_ENDPOINTCONFIG_1**:服務名無效 `<!--<given value>-->`:必須是「dataSource」或「action」


潛在警告是：

**ERR_ENDPOINTCONFIG_106**:限定配置：未定義的最大HTTP連接數：預設不限制



## 使用案例

在本節中，您會找到可在[!DNL Journey Orchestration]中管理上限設定的五個主要使用案例。

為協助您進行測試和設定，可在[此處](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)取得Postman集合。

此Postman集合已設定為共用透過&#x200B;__[Adobe I/O控制台的Integrations](https://console.adobe.io/integrations) > Try it out > Download for Postman__&#x200B;產生的Postman變數集合，此集合會產生包含所選整合值的Postman環境檔案。

下載並上傳至Postman後，您需要新增三個變數：`{JO_HOST}`、`{Base_Path}`和`{SANDBOX_NAME}`。
* `{JO_HOST}` : [!DNL Journey Orchestration] 網關URL
* `{BASE_PATH}` :API的進入點。值為「/authoring」
* `{SANDBOX_NAME}` :與 **執行API作業的沙箱名稱** （例如&#39;prod&#39;）對應的標頭x-sandbox-name。如需詳細資訊，請參閱[沙箱概述](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html) 。

在下節中，您會找到Rest API呼叫排序清單以執行使用案例。

使用案例n°1:**建立和部署新的上限設定**

1. 清單
1. 建立
1. candeploy
1. 部署

使用案例n°2:**更新並部署尚未部署的上限配置**

1. 清單
1. get
1. 更新
1. candeploy
1. 部署

用例n°3:**取消部署並刪除已部署的上限配置**

1. 清單
1. 取消部署
1. 刪除

使用案例n°4:**刪除已部署的上限配置。**

在僅一個API呼叫中，您可以使用forceDelete參數來取消部署和刪除設定。
1. 清單
1. 刪除，使用forceDelete參數

使用案例n°5:**更新已部署的上限配置**

1. 清單
1. get
1. 更新
1. 取消部署
1. candeploy
1. 部署
