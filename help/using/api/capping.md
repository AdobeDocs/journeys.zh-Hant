---
title: 設定API說明上限
description: 進一步瞭解封閉API。
contentOwner: sauviat
products: journeys
audience: audiences
content-type: reference
topic-tags: journeys
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9f28bdc0e74359ff9f8d84961769b84973ae3f39
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 1%

---


# 使用封閉API

## 簡介

Journey Orchestration的API支援5000個事件／秒，但某些外部系統或API的總處理能力無法相同。 因此，Journey Orchestration隨附一個稱為Capping API的專屬功能，可監控並限制我們對外部系統的速率。

在資料來源設定期間，您將定義系統連線，以擷取將用於歷程的其他資訊，或是用於動作定義，您將設定協力廠商系統連線，以傳送訊息或API呼叫。 每次由Journey執行API呼叫時，即會查詢封頂API，呼叫會透過API引擎。 如果已定義限制，則拒絕調用，外部系統不會過載。

如需動作或資料來源設定的詳細資訊，請參 [閱關於動作](https://docs.adobe.com/content/help/en/journeys/using/action-journeys/action.html)[或關於資料來源](https://docs.adobe.com/content/help/en/journeys/using/data-source-journeys/about-data-sources.html)


## 資源

Journey Orchestration Capping API是在此處提供的Swagger檔案中 [說明](https://adobedocs.github.io/JourneyAPI/docs/)。

若要將此API與您的Journey Orchestration例項搭配使用，您必須使用AdobeIO Console。 您可以先遵循本「Adobe Developer Console [快速入門」](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) ，然後使用本頁中的章節。

若要測試並準備整合，此處提供Postman [系列](https://github.com/AdobeDocs/JourneyAPI/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)。

## 驗證

### 設定 API 存取

Journey Orchestration API存取權是透過下列步驟設定。 這些步驟在 [Adobe IO檔案中有詳細說明](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)。

>[!CAUTION]
>
>若要在Adobe IO中管理憑證，請確定您在「管理控制台」中 <b>擁有組織或開發人</b> 員帳戶的系統管 <a href="https://helpx.adobe.com/enterprise/using/manage-developers.html">理員</a> 權限。

1. **檢查您是否有數位憑證**，或視需要建立憑證。 在下列步驟中，需要隨憑證提供的公開金鑰和私密金鑰。
1. **在Adobe IO中建立與Journey Orchestration Service的新整合** ，並加以設定。 Journey Orchestration和Adobe Experience Platform需要產品設定檔存取。 然後會產生您的認證（API金鑰、用戶端密碼……）。
1. **從先前產生的認證建立JSON Web Token(JWT)** ，並使用您的私密金鑰簽名。 JWT會對Adobe驗證您的身分並授與您API存取權所需的所有身分與安全資訊進行編碼。 本節將詳述此步 [驟](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **透過POST要求或透過Developer Console介面** ，將您的JWT交換為存取Token。 此存取Token必須用於API請求的每個標題中。

若要建立安全的服務對服務Adobe I/O API作業階段，對Adobe服務的每個要求都必須在「授權」標題中包含下列資訊。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>**: 這是您的個人組織ID,Adobe會針對每個例項提供一個組織ID:

   * &lt;ORGANIZATION> : 您的生產實例
   若要取得您的組織ID值，請洽詢您的管理員或Adobe技術聯絡人。 建立新整合時，您也可以在授權清單(請參閱 <a href="https://www.adobe.io/authentication.html">Adobe IO檔案</a>)中擷取它至Adobe I/O。

* **&lt;ACCESS_TOKEN>**: 透過POST請求交換JWT時擷取的個人存取Token。

* **&lt;API_KEY>**: 您的個人API金鑰。 在建立與Journey Orchestration Service的全新整合後，Adobe I/O中就提供了它。



## 設定API說明上限

「設定上限API」可協助您建立、設定和監控您的設定上限。

| 方法 | 路徑 | 說明 |
|---|---|---|
| 貼文 | list/endpointConfigs | 獲取端點封閉配置的清單 |
| 貼文 | /endpointConfigs | 建立端點封閉配置 |
| 貼文 | /endpointConfigs/{uid}/deploy | 部署端點封閉配置 |
| 貼文 | /endpointConfigs/{uid}/undeploy | 取消部署端點封閉配置 |
| 貼文 | /endpointConfigs/{uid}/canDeploy | 檢查是否可部署端點封閉配置 |
| PUT | /endpointConfigs/{uid} | 更新端點封閉配置 |
| 取得 | /endpointConfigs/{uid} | 檢索端點封閉配置 |
| 刪除 | /endpointConfigs/{uid} | 刪除引入點封閉配置 |

當建立或更新配置時，會自動執行檢查，以確保裝載的語法和完整性。
如果發生某些問題，操作將返回警告或錯誤，以幫助您更正配置。



## 端點配置

以下是端點配置的基本結構：

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

### 例如：

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


## 警告與錯誤

當呼叫 **canDeploy方法時** ，流程會驗證配置並返回由其唯一ID標識的驗證狀態，其中一種方式為：

```
"ok" or "error"
```

可能的錯誤有：

* **ERR_ENDPOINTCONFIG_100**: 上限設定： 遺失或無效的URL
* **ERR_ENDPOINTCONFIG_101**: 上限設定： 格式錯誤的url
* **ERR_ENDPOINTCONFIG_102**: 上限設定： 格式錯誤的url: host:port中不允許在URL中使用通配符
* **ERR_ENDPOINTCONFIG_103**: 上限設定： 缺少HTTP方法
* **ERR_ENDPOINTCONFIG_104**: 上限設定： 未定義呼叫評分
* **ERR_ENDPOINTCONFIG_107**: 上限設定： 無效的最大呼叫計數(maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**: 上限設定： 無效的最大呼叫計數(periodInMs)
* **ERR_ENDPOINTCONFIG_111**: 上限設定： 無法建立端點配置： 無效載荷
* **ERR_ENDPOINTCONFIG_112**: 上限設定： 無法建立端點配置： 需要JSON裝載
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: 無效的服務名 <!--<given value>-->稱： 必須是&#39;dataSource&#39;或&#39;action&#39;


潛在警告是：

**ERR_ENDPOINTCONFIG_106**: 上限設定： 未定義最大HTTP連接數： 預設情況下不限制



## 使用案例

在本節中，您將會找到在「歷程協調」中管理上限設定時可執行的五個主要使用案例。

為協助您進行測試和設定，此處提供Postman [系列](https://github.com/AdobeDocs/JourneyAPI/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)。

此Postman Collection已設定為共用透過 __[Adobe I/O Console的「整合](https://console.adobe.io/integrations)>試用>下載Postman」產生的Postman Variable集合，而Postman__&#x200B;會產生具有選取整合值的Postman Environment檔案。

下載並上傳至Postman後，您需要新增兩個變數： `{JO_HOST}` 和 `{Base_Path}`。
* `{JO_HOST}` : 歷程協調閘道URL
* `{BASE_PATH}` : API的入口點。 值為&#39;/authoring&#39;



使用案例n°1: **建立和部署新的封閉組態**

1. 清單
1. creat
1. candeploy
1. 部署

使用案例n°2: **更新和部署尚未部署的封閉設定**

1. 清單
1. get
1. 更新
1. candeploy
1. 部署

使用案例n°3: **取消部署和刪除已部署的封閉配置**

1. 清單
1. 取消部署
1. 刪除

使用案例n°4: **刪除已部署的封閉配置。**

在僅一個API呼叫中，您可以使用forceDelete參數解除部署和刪除設定。
1. 清單
1. 刪除，使用forceDelete param

使用案例n°5: **更新已部署的上限設定**

1. 清單
1. get
1. 更新
1. 取消部署
1. candeploy
1. 部署
