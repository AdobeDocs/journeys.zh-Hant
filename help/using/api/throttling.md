---
product: adobe campaign
title: 使用限制API
description: 進一步了解Throttling API
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 76afe397-3e18-4e01-9b0b-c21705927ce2
source-git-commit: 25d8dcd027f3f433759ce97f9a3a1dad85ba1427
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 2%

---

# 使用限制API

節流API可協助您建立、設定和監控節流設定，以限制每秒傳送的事件數。

>[!IMPORTANT]
>
>目前每個組織僅允許一個配置。 必須在生產沙箱上定義設定（透過標題中的x-sandbox-name提供）。
>
>組織層級會套用設定。
>
>達到API中設定的限制時，會將更多事件排入佇列，最多6小時。 無法修改此值。

## 限制API說明 {#description}

| 方法 | 路徑 | 說明 |
|---|---|---|
| [!DNL POST] | list/throttlingConfigs | 獲取限制配置的清單 |
| [!DNL POST] | /throttlingConfigs | 建立限制配置 |
| [!DNL POST] | /throttlingConfigs/`{uid}`/deploy | 部署調節配置 |
| [!DNL POST] | /throttlingConfigs/`{uid}`/undeploy | 取消部署調節配置 |
| [!DNL POST] | /throttlingConfigs/`{uid}`/canDeploy | 檢查是否可以部署限制配置 |
| [!DNL PUT] | /throttlingConfigs/`{uid}` | 更新限制配置 |
| [!DNL GET] | /throttlingConfigs/`{uid}` | 檢索限制配置 |
| [!DNL DELETE] | /throttlingConfigs/`{uid}` | 刪除限制配置 |

## 調節配置 {#configuration}

以下是節流配置的結構。 **名稱** 和 **說明** 屬性為選用。

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

建立或更新設定時，程式會驗證指定的設定，並傳回以其唯一ID識別的驗證狀態，其中一項為：

```
"ok" or "error"
```

>[!IMPORTANT]
>
>屬性 **maxThroughput**, **urlPattern** 和 **方法** 是必填的。
>
>**maxThroughput** 值必須在200-5000範圍內。

建立、刪除或部署節流配置時，可能會發生以下錯誤：

* **ERR_THROTTLING_CONFIG_100**:限制配置： `<mandatory attribute>` 必填
* **ERR_THROTTLING_CONFIG_101**:限制配置：maxThroughput是必需的，且必須大於或等於200且小於或等於5000
* **ERR_THROTTLING_CONFIG_104**:限制配置：格式錯誤的url模式
* **ERR_THROTTLING_CONFIG_105**:限制配置：url模式的主機部分不允許萬用字元
* **ERR_THROTTLING_CONFIG_106**:限制配置：有效負載
* **THROTTLING_CONFIG_CONFIG_FORBIDDEN_ERROR:DELETE:1456**，「無法刪除已部署的限制配置。 請先取消部署再刪除&quot;
* **THROTTLING_CONFIG_DELETE_錯誤：1457**, &quot;無法刪除限制配置：意外錯誤發生&quot;
* **THROTTLING_CONFIG_DEPLOY_ERROR:1458**，「無法部署限制配置：意外錯誤發生&quot;
* **THROTTLING_CONFIG_UNDEPLOY_ERROR:1459**，「無法取消部署限制配置：意外錯誤發生&quot;
* **THROTTLING_CONFIG_ERROR:GET:1460**，「無法獲取限制配置：意外錯誤發生&quot;
* **THROTTLING_CONFIG_UPDATE_NOT_ACTIVE_ERROR:1461**, &quot;無法更新限制配置：運行時版本不活動&quot;
* **THROTTLING_CONFIG_UPDATE_ERROR:1462**, &quot;無法更新限制配置：意外錯誤發生&quot;
* **THROTTLING_CONFIG_NON_PROD_SANDBOX_ERROR:1463**, &quot;禁止對節流配置執行操作：non prod sandbox&quot;
* **THROTTLING_CONFIG_CREATE_ERROR:1464**, &quot;無法建立限制配置：意外錯誤發生&quot;
* **THROTTLING_CONFIG_CREATE_LIMIT_ERROR:1465**, &quot;無法建立限制配置：每個組織僅允許一個配置
* **THROTTLING_CONFIG_ALEADY_DEPLOYED_ERROR:14466**，「無法部署限制配置：已部署
* **THROTTLING_CONFIG_NOT_FOUND_ERROR:14467**, &quot;未找到節流配置&quot;
* **THROTTLING_CONFIG_NOT_DEPLOYED_ERROR:14468**，「無法取消部署限制配置：尚未部署

**錯誤範例**

嘗試在非生產沙箱上建立設定時：

```
{
    "status": 400,
    "error": "{\"code\":1463,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Operation not allowed on throttling config: non prod sandbox\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:384\",\"schema\":\"throttlingConfigs$ui-tests\"}",
    "requestId": "5sgnAYXs8mpswwjAFEIaAU2faQYbtyHc"
}
```

如果給定的sanbox不存在：

```
{
    "status": 500,
    "error": "{\"code\":4000,\"family\":\"INTERNAL_ERROR\",\"message\":\"INTERNAL ERROR\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.common.exceptions.ApiErrorException:43\"}",
    "requestId": "04ZJ4e5ki4bYs3lfO17a7hovRGewjvdK"
}
```

嘗試建立其他配置時：

```
{
    "status": 400,
    "error": "{\"code\":1465,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Can't create throttling config: only one config allowed per org\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:108\",\"schema\":\"throttlingConfigs$prod\"}",
    "requestId": "A7ezT8JhOQT4WIAf1Fv7K2wCDA8281qM"
}
```

## 使用案例 {#uc}

為協助您進行測試和設定，可使用Postman集合 [此處](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Throttling-API_postman-collection.json).

此Postman集合已設定為共用透過 __[Adobe I/O主控台的整合](https://console.adobe.io/tw/integrations) >試用>下載Postman__，會產生包含選取整合值的Postman環境檔案。

下載並上傳至Postman後，您需要新增三個變數： `{JO_HOST}`,`{BASE_PATH}` 和 `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] 網關URL
* `{BASE_PATH}` :API的進入點。 值為「/authoring」
* `{SANDBOX_NAME}` :標題 **x-sandbox-name** （例如&#39;prod&#39;），此名稱對應於將進行API操作的沙箱名稱。 請參閱 [沙箱概述](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=zh-Hant) 以取得更多資訊。

在下節中，您會找到Rest API呼叫排序清單以執行使用案例。

使用案例n°1: **建立和部署新的節流配置**

1. list
1. 建立
1. candeploy
1. 部署

使用案例n°2: **更新並部署尚未部署的調節配置**

1. list
1. get
1. 更新
1. candeploy
1. 部署

用例n°3: **取消部署並刪除已部署的節流配置**

1. list
1. 取消部署
1. 刪除

使用案例n°4: **刪除已部署的節流配置**

在僅一個API呼叫中，您可以使用forceDelete參數來取消部署和刪除設定。

1. list
1. 刪除，使用forceDelete參數

使用案例n°5: **更新已部署的限制配置**

>[!NOTE]
>
>更新前不需要取消部署配置

1. list
1. get
1. 更新

## 在運行時級配置生命週期 {#config}

取消部署設定時，會在執行階段層級將其標示為非作用中，且24小時內會繼續處理待定事件。 然後，它會刪除在執行階段服務中。

取消部署配置後，可以更新和重新部署配置。 這將建立新的執行階段設定，並在後續動作執行中考量。

更新已部署的設定時，會立即考慮新值。 自動調整基礎系統資源。 與取消部署然後重新部署配置相比，這是最佳選擇。

## 回應範例 {#responses}

**建立 — POST**

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

**更新 — PUT**

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

**讀取（更新後） — GET**

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

**讀取（部署後） — GET**

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
