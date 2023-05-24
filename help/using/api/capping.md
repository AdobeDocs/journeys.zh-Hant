---
product: adobe campaign
title: 封頂API說明
description: 瞭解有關封頂API的更多資訊。
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: 1f91bae24dfcb291dd354e4bff9eab85afdaf5a1
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 32%

---


# 使用封蓋API {#work}

上限設定API可幫助您建立、配置和監視上限設定配置。

## 封頂API說明

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

## 使用案例

在本節中，您將發現可以執行的五個主要用例，以管理中的封蓋配置 [!DNL Journey Orchestration]。

為協助您進行測試和設定，可在[此處](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)取得 Postman 集合。

此 Postman 集合已設定為共用透過 __[Adobe I/O 主控台的整合](https://console.adobe.io/integrations)產生的 Postman 變數集合 > 試用 > 下載 Postman__，會產生包含選取整合值的 Postman 環境檔案。

一旦下載並上傳至 Postman，您需要新增三個變數：`{JO_HOST}`、`{BASE_PATH}`以及`{SANDBOX_NAME}`。
* `{JO_HOST}` : [!DNL Journey Orchestration]閘道 URL
* `{BASE_PATH}`：API 的進入點。 值為「/authoring」
* `{SANDBOX_NAME}`：標題 **x-sandbox-name** (例如，&#39;prod&#39;)，此名稱對應於將進行 API 操作的沙箱名稱。如需詳細資訊，請參閱[沙箱概觀](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=zh-Hant)。

您將在下節找到用於執行使用案例的 Rest API 呼叫排序清單。

用例n°1: **建立和部署新的封頂配置**

1. list
1. create
1. candeploy
1. deploy

用例n°2: **更新和部署尚未部署的上限配置**

1. list
1. get
1. update
1. candeploy
1. deploy

用例n°3: **取消部署和刪除已部署的封頂配置**

1. list
1. undeploy
1. delete

用例n°4: **刪除已部署的封頂配置。**

在僅一個 API 呼叫，您可以使用 forceDelete 參數來取消部署和刪除設定。
1. list
1. 刪除，使用 forceDelete 參數

用例n°5: **更新已部署的封頂配置**

1. list
1. get
1. update
1. undeploy
1. candeploy
1. deploy
