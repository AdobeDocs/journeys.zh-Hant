---
product: adobe campaign
title: 封頂API說明
description: 瞭解有關封頂API的更多資訊。
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: a32a208fcaef9a408c850c0ad74ab44e3eb44709
workflow-type: tm+mt
source-wordcount: '1173'
ht-degree: 3%

---

# 使用封蓋API

## 簡介

[!DNL Journey Orchestration]的API支援5000個事件/秒，但某些外部系統或API不能具有等效的吞吐量。 所以 [!DNL Journey Orchestration] 附帶了一個稱為Capping API的專用功能，用於監控和限制我們施加給外部系統的速率。

在資料源配置期間，您將定義到系統的連接以檢索將用於您的行程的其他資訊，或者為操作定義，您將配置第三方系統的連接以發送消息或API調用。 每次由Journey執行API調用時，查詢封頂API，調用通過API引擎。 如果定義了限制，則呼叫被拒絕，外部系統不會過載。

對於外部資料源，每秒最大調用數設定為15。 如果呼叫數超過每秒15次，則放棄剩餘的呼叫。 您可以增加私有外部資料源的此限制。 聯繫Adobe，將端點包括在允許清單中。 對於公共外部資料源，這是不可能的。 要瞭解有關整合外部系統時的最佳做法和保證的更多資訊，請參閱此 [頁](../about/external-systems.md)。

要瞭解有關操作或資料源配置的詳細資訊，請參見 [關於操作](https://experienceleague.adobe.com/docs/journeys/using/action-journeys/action.html) 或 [關於資料源](https://experienceleague.adobe.com/docs/journeys/using/data-source-journeys/about-data-sources.html)

## 資源

>[!NOTE]
>
>的 [!DNL Journey Orchestration] 在可用的Swagger檔案中描述了封蓋API [這裡](https://adobedocs.github.io/JourneyAPI/docs/)。

將此API與 [!DNL Journey Orchestration] 實例，您需要使用AdobeI/O控制台。 您可以按照此操作 [Adobe開發人員控制台入門](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) 然後使用此頁中的部分。

要test和準備您的整合，可提供Postman收藏 [這裡](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)。

## 驗證

### 設定 API 存取

[!DNL Journey Orchestration] API訪問通過以下步驟設定。 以下每個步驟均在 [Adobe I/O文檔](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)。

>[!CAUTION]
>
>要在Adobe I/O中管理證書，請確保 <b>系統管理員</b> 組織或 [開發者帳戶](https://helpx.adobe.com/tw/enterprise/using/manage-developers.html) 在管理控制台中。

1. **檢查您有數字證書**，或根據需要建立。 在以下步驟中需要隨證書提供的公鑰和私鑰。
1. **建立新整合到 [!DNL Journey Orchestration] 服務** Adobe I/O並配置。 需要產品配置檔案訪問 [!DNL Journey Orchestration] 和Adobe Experience Platform。 然後將生成您的憑據（API密鑰、客戶端密鑰……）。
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

   要獲取您的組織ID值，請咨詢您的管理員或Adobe技術聯繫人。 建立新整合時，您還可以在許可證清單中將其檢索到Adobe I/O(請參見 <a href="https://www.adobe.io/authentication.html">Adobe I/O文檔</a>)。

* **&lt;access_token>**:通過POST請求交換JWT時檢索的個人訪問令牌。

* **&lt;api_key>**:您的個人API密鑰。 在建立新整合後在Adobe I/O中提供 [!DNL Journey Orchestration] 服務。



## 封頂API說明

上限設定API可幫助您建立、配置和監視上限設定配置。

| 方法 | 路徑 | 說明 |
|---|---|---|
| [!DNL POST] | list/endpointConfigs | 獲取端點封頂配置清單 |
| [!DNL POST] | /endpointConfigs | 建立端點封頂配置 |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | 部署終結點封頂配置 |
| [!DNL POST] | /endpointConfigs/`{uid}`/取消部署 | 取消部署終結點封頂配置 |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | 檢查是否可以部署終結點封頂配置 |
| [!DNL PUT] | /endpointConfigs/`{uid}` | 更新終結點封蓋配置 |
| [!DNL GET] | /endpointConfigs/`{uid}` | 檢索端點封蓋配置 |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | 刪除入口點封頂配置 |

當建立或更新配置時，將自動執行檢查以保證有效負載的語法和完整性。
如果出現一些問題，該操作將返回警告或錯誤以幫助您更正配置。



## 終結點配置

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

### 範例：

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

當 **可部署** 方法被調用，進程驗證配置並返回由其唯一ID標識的驗證狀態：

```
"ok" or "error"
```

潛在錯誤有：

* **ERR_ENDPOINTCONFIG_100**:上限配置：缺少或無效的url
* **ERR_ENDPOINTCONFIG_101**:上限配置：格式
* **ERR_ENDPOINTCONFIG_102**:上限配置：格式錯誤的url:host:port中不允許在url中使用通配符
* **ERR_ENDPOINTCONFIG_103**:上限配置：缺少HTTP方法
* **ERR_ENDPOINTCONFIG_104**:上限配置：未定義呼叫評級
* **ERR_ENDPOINTCONFIG_107**:上限配置：無效的最大調用計數(maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**:上限配置：最大調用計數無效(periodInMs)
* **ERR_ENDPOINTCONFIG_111**:上限配置：無法建立終結點配置：無效負載
* **ERR_ENDPOINTCONFIG_112**:上限配置：無法建立終結點配置：應為JSON負載
* **ERR_AUTHORING_ENDPOINTCONFIG_1**:無效的服務名稱 `<!--<given value>-->`:必須是「dataSource」或「action」


潛在警告是：

**ERR_ENDPOINTCONFIG_106**:上限配置：未定義最大HTTP連接數：預設情況下不限制



## 用例

在本節中，您將發現可以執行的五個主要用例，以管理中的封蓋配置 [!DNL Journey Orchestration]。

為幫助您進行測試和配置，提供了Postman收藏 [這裡](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)。

此Postman集合已設定為共用通過 __[Adobe I/O控制台的整合](https://console.adobe.io/tw/integrations) >試用>下載Postman__，生成具有選定整合值的Postman環境檔案。

下載並上傳到Postman後，需要添加三個變數： `{JO_HOST}`。`{Base_Path}` 和 `{SANDBOX_NAME}`。
* `{JO_HOST}` : [!DNL Journey Orchestration] 網關URL
* `{BASE_PATH}` :API的入口點。 值為「/authoring」
* `{SANDBOX_NAME}` :標題 **x-sandbox-name** （例如，「prod」），與API操作將在其中進行的沙盒名稱相對應。 查看 [箱概述](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=zh-Hant) 的子菜單。

在以下部分中，您將找到Rest API調用排序清單以執行用例。

用例n°1: **建立和部署新的封頂配置**

1. list
1. 建立
1. 部署
1. 部署

用例n°2: **更新和部署尚未部署的上限配置**

1. 清單
1. get
1. 更新
1. 部署
1. 部署

用例n°3: **取消部署和刪除已部署的封頂配置**

1. 清單
1. 取消部署
1. 刪除

用例n°4: **刪除已部署的封頂配置。**

在僅一個API調用中，可以使用forceDelete參數取消部署和刪除配置。
1. 清單
1. 刪除，使用forceDelete參數

用例n°5: **更新已部署的封頂配置**

1. 清單
1. 得
1. 更新
1. 取消部署
1. 部署
1. 部署
