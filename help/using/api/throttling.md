---
product: adobe campaign
title: 使用節流 API
description: 深入了解節流 API
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 76afe397-3e18-4e01-9b0b-c21705927ce2
source-git-commit: 7b8c9d2bfe244b040a9064a7a240ea6f43cc8b41
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 96%

---

# 使用節流 API

節流API可協助您建立、設定和監視節流設定，以限制每秒傳送的事件數。

>[!IMPORTANT]
>
>目前每個組織僅允許一個設定。 必須在生產沙箱上定義設定 (透過標題中的 x-sandbox-name 提供)。
>
>組織層級會套用設定。
>
>當達到 API 設定的限制時，會將更多事件排入佇列，最多 6 小時。 無法修改此值。

## 節流 API 說明 {#description}

| 方法 | 路徑 | 說明 |
|---|---|---|
| [!DNL POST] | list/throttlingConfigs | 取得節流設定的清單 |
| [!DNL POST] | /throttlingConfigs | 建立節流設定 |
| [!DNL POST] | /throttlingConfigs/`{uid}`/deploy | 部署節流設定 |
| [!DNL POST] | /throttlingConfigs/`{uid}`/undeploy | 取消部署節流設定 |
| [!DNL POST] | /throttlingConfigs/`{uid}`/canDeploy | 檢查是否可以部署節流設定 |
| [!DNL PUT] | /throttlingConfigs/`{uid}` | 更新節流設定 |
| [!DNL GET] | /throttlingConfigs/`{uid}` | 擷取節流設定 |
| [!DNL DELETE] | /throttlingConfigs/`{uid}` | 刪除節流設定 |

## 節流設定{#configuration}

以下是節流設定的結構。 **name**&#x200B;及&#x200B;**description**&#x200B;屬性為選用。

```
{
    "name": "<given name - free text>",
    "description": "<given description - free text>"
    "urlPattern": "<endpoint URL - wildcards are allowed>",
    "methods": [ "<HTTP method such as GET, POST, PUT>" ],
    "maxThroughput": <max call throughput>
}
```

範例：

```
{
  "name": "throttling-config-external",
  "description": "example of throttling config for an external endpoint",
  "urlPattern": "https://api.example.org/data/2.5/*",
  "methods": ["POST", "PUT"],
  "maxThroughput": 4000
}
```

## 錯誤

建立或更新設定時，流程會驗證指定的設定，並傳回以其唯一 ID 識別的驗證狀態，其中一項為：

```
"ok" or "error"
```

>[!IMPORTANT]
>
>屬性 **maxThroughput**、**urlPattern**&#x200B;及&#x200B;**方法**&#x200B;為必填。
>
>**maxThroughput** 值必須在 200-5000 範圍內。

當建立、刪除或部署節流設定時，可能會發生以下錯誤：

* **ERR_THROTTLING_CONFIG_100**：節流設定：`<mandatory attribute>`必填
* **ERR_THROTTLING_CONFIG_101**：節流設定：maxThroughput 為必填，且必須大於或等於 200 且小於或等於 5000
* **ERR_THROTTLING_CONFIG_104**：節流設定：格式錯誤的 URL 模式
* **ERR_THROTTLING_CONFIG_105**：節流設定：URL 模式的主機部分不允許使用萬用字元
* **ERR_THROTTLING_CONFIG_106**：節流設定：無效負載
* **THROTTLING_CONFIG_DELETE_FORBIDDEN_ERROR: 1456**，「無法刪除已部署的節流設定。 請先取消部署再刪除」
* **THROTTLING_CONFIG_DELETE_ERROR: 1457**，「無法刪除節流設定：發生意外錯誤」
* **THROTTLING_CONFIG_DEPLOY_ERROR: 1458**，「無法部署節流設定：發生意外錯誤」
* **THROTTLING_CONFIG_UNDEPLOY_ERROR: 1459**，「無法取消部署節流設定：發生意外錯誤」
* **THROTTLING_CONFIG_GET_ERROR: 1460**，「無法取得節流設定：發生意外錯誤」
* **THROTTLING_CONFIG_UPDATE_NOT_ACTIVE_ERROR: 1461**，「無法更新節流設定：執行時版本未處於活動狀態」
* **THROTTLING_CONFIG_UPDATE_ERROR: 1462**，「無法更新節流設定：發生意外錯誤」 
* **THROTTLING_CONFIG_NON_PROD_SANDBOX_ERROR: 1463**，「禁止對節流設定執行操作：非生產沙箱」 
* **THROTTLING_CONFIG_CREATE_ERROR: 1464**，「無法建立節流設定：發生意外錯誤」
* **THROTTLING_CONFIG_CREATE_LIMIT_ERROR: 1465**，「無法建立節流設定：每個組織僅允許一個設定」
* **THROTTLING_CONFIG_ALREADY_DEPLOYED_ERROR: 14466**，「無法部署節流設定：已部署」
* **THROTTLING_CONFIG_NOT_FOUND_ERROR: 14467**，「未找到節流設定」
* **THROTTLING_CONFIG_NOT_DEPLOYED_ERROR: 14468**，「無法取消部署節流設定：尚未部署」

**錯誤範例**

當嘗試在非生產沙箱上建立設定時：

```
{
    "status": 400,
    "error": "{\"code\":1463,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Operation not allowed on throttling config: non prod sandbox\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:384\",\"schema\":\"throttlingConfigs$ui-tests\"}",
    "requestId": "5sgnAYXs8mpswwjAFEIaAU2faQYbtyHc"
}
```

如果給定的沙箱不存在：

```
{
    "status": 500,
    "error": "{\"code\":4000,\"family\":\"INTERNAL_ERROR\",\"message\":\"INTERNAL ERROR\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.common.exceptions.ApiErrorException:43\"}",
    "requestId": "04ZJ4e5ki4bYs3lfO17a7hovRGewjvdK"
}
```

當嘗試建立其他設定時：

```
{
    "status": 400,
    "error": "{\"code\":1465,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Can't create throttling config: only one config allowed per org\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:108\",\"schema\":\"throttlingConfigs$prod\"}",
    "requestId": "A7ezT8JhOQT4WIAf1Fv7K2wCDA8281qM"
}
```

## 使用案例 {#uc}

為協助您進行測試和設定，可在[此處](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Throttling-API_postman-collection.json)取得 Postman 集合。

此 Postman 集合已設定為共用透過 __[Adobe I/O 主控台的整合](https://console.adobe.io/integrations)產生的 Postman 變數集合 > 試用 > 下載 Postman__，會產生包含選取整合值的 Postman 環境檔案。

一旦下載並上傳至 Postman，您需要新增三個變數：`{JO_HOST}`、`{BASE_PATH}`以及`{SANDBOX_NAME}`。
* `{JO_HOST}` : [!DNL Journey Orchestration]閘道 URL
* `{BASE_PATH}`：API 的進入點。 值為「/authoring」
* `{SANDBOX_NAME}`：標題 **x-sandbox-name** (例如，&#39;prod&#39;)，此名稱對應於將進行 API 操作的沙箱名稱。如需詳細資訊，請參閱[沙箱概觀](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=zh-Hant)。

您將在下節找到用於執行使用案例的 Rest API 呼叫排序清單。

使用案例 n°1：**建立和部署新的節流設定**

1. list
1. create
1. candeploy
1. deploy

使用案例 n°2：**更新並部署尚未部署的節流設定**

1. list
1. get
1. update
1. candeploy
1. deploy

使用案例 n°3：**取消部署並刪除已部署的節流設定**

1. list
1. undeploy
1. delete

使用案例 n°4：**刪除已部署的節流設定**

在僅一個 API 呼叫，您可以使用 forceDelete 參數來取消部署和刪除設定。

1. list
1. 刪除，使用 forceDelete 參數

使用案例 n°5：**更新已部署的節流設定**

>[!NOTE]
>
>更新前不需要取消部署設定

1. list
1. get
1. update

## 在執行階段層級設定生命週期 {#config}

當取消部署設定時，會在執行階段層級將其標示為非活動狀態，且 24 小時內會繼續處理擱置事件。 然後，在執行階段服務將其刪除。

取消部署設定後，可以更新和重新部署設定。 這將建立新的執行階段設定，將在即將執行的動作中考慮該設定。

當更新已部署的設定時，會立即考慮新值。自動調整基礎系統資源。 與取消部署然後重新部署設定相比，這是最佳選擇。

## 回應範例 {#responses}

**建立 - POST**

```
{
    "canDeploy": {
        "validationStatus": "ok"
    },
    "createdElement": {
        "name": "throttling-config-external",
        "description": "example of throttling config for an external endpoint",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "PUT",
            "POST"
        ],
        "maxThroughput": 4000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T10:48:16.099647Z"
        },
        "state": "created",
        "authoringFormatVersion": "1.0"
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "created"
}
```

**更新 - PUT**

```
{
    "updatedElement": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "updated",
    "canDeploy": {
        "validationStatus": "ok"
    }
}
```

**讀取 (更新後) - GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    }
}
```

**讀取 (部署後) - GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "authoringFormatVersion": "1.0",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "version": "1.0",
        "state": "deployed",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z",
            "lastDeployedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastDeployedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastDeployedAt": "2023-03-22T11:46:07.532648Z"
        },
        "hasBeenDeployed": true
    }
}
```
