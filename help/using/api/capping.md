---
product: adobe campaign
title: 設定API說明上限
description: 進一步瞭解上限API。
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 27%

---


# 使用上限API {#work}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_


上限API可幫助您建立、設定和監控您的上限設定。

## 設定API說明上限

| 方法 | 路徑 | 說明 |
|---|---|---|
| [!DNL POST] | list/endpointConfig | 取得端點上限設定清單 |
| [!DNL POST] | /endpointConfigs | 建立端點上限設定 |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | 部署端點上限設定 |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeploy | 取消部署端點上限設定 |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | 檢查是否可以部署端點上限設定 |
| [!DNL PUT] | /endpointConfigs/`{uid}` | 更新端點上限設定 |
| [!DNL GET] | /endpointConfigs/`{uid}` | 擷取端點上限設定 |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | 刪除端點上限設定 |

建立或更新設定時，會自動執行檢查以確保語法和裝載的完整性。
如果發生某些問題，作業會傳回警告或錯誤，以協助您更正設定。

## 端點設定

以下是端點設定的基本結構：

```
{
    "url": "<endpoint URL>",  //wildcards are allowed in the endpoint URL
    "methods": [ "<HTTP method such as GET, POST, >, ...],
    "services": {
        "<service name>": { . //must be "action" or "dataSource" 
            "maxHttpConnections": <max connections count to the endpoint (optional)>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

>[!IMPORTANT]
>
>**maxHttpConnections**&#x200B;引數是選用的。 它可讓您限制Journey Optimizer將開啟給外部系統的連線數量。
>
>可設定的最大值為400。 如果未指定任何專案，則系統可能會開啟數千個連線，視系統的動態縮放而定。

### 範例：

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "maxHttpConnections": 50,
      "rating": {
        "maxCallsCount": 500,
        "periodInMs": 1000
      }
    }
  },
  "orgId": "<IMS Org Id>"
}
```

## 警告和錯誤

呼叫&#x200B;**canDeploy**&#x200B;方法時，程式會驗證設定並傳回由其唯一識別碼識別的驗證狀態：

```
"ok" or "error"
```

可能的錯誤包括：

* **ERR_ENDPOINTCONFIG_100**：設定上限：遺漏或無效的url
* **ERR_ENDPOINTCONFIG_101**：上限設定：格式錯誤的url
* **ERR_ENDPOINTCONFIG_102**：上限設定：格式錯誤的url：不允許在host：port中使用url中的wildchar
* **ERR_ENDPOINTCONFIG_103**：上限設定：遺失HTTP方法
* **ERR_ENDPOINTCONFIG_104**：上限設定：未定義任何通話分級
* **ERR_ENDPOINTCONFIG_107**：上限設定：無效的最大呼叫計數(maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**：上限設定：無效的最大呼叫計數(periodInMs)
* **ERR_ENDPOINTCONFIG_111**：上限設定：無法建立端點設定：無效的承載
* **ERR_ENDPOINTCONFIG_112**：上限設定：無法建立端點設定：需要JSON裝載
* **ERR_AUTHORING_ENDPOINTCONFIG_1**：無效的服務名稱`<!--<given value>-->`：必須為&#39;dataSource&#39;或&#39;action&#39;

可能的警告為：

**ERR_ENDPOINTCONFIG_106**：上限設定：未定義最大HTTP連線：預設無限制

## 使用案例

在本節中，您將會找到五個主要使用案例，您可執行這些案例來管理[!DNL Journey Orchestration]中的上限設定。

為協助您進行測試和設定，可在[此處](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)取得 Postman 集合。

此 Postman 集合已設定為共用透過 __[Adobe I/O 主控台的整合](https://console.adobe.io/integrations)產生的 Postman 變數集合 > 試用 > 下載 Postman__，會產生包含選取整合值的 Postman 環境檔案。

一旦下載並上傳至 Postman，您需要新增三個變數：`{JO_HOST}`、`{BASE_PATH}`以及`{SANDBOX_NAME}`。
* `{JO_HOST}` : [!DNL Journey Orchestration]閘道 URL
* `{BASE_PATH}`：API 的進入點。 值為「/authoring」
* `{SANDBOX_NAME}`：標題 **x-sandbox-name** (例如，&#39;prod&#39;)，此名稱對應於將進行 API 操作的沙箱名稱。如需詳細資訊，請參閱[沙箱概觀](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=zh-Hant)。

您將在下節找到用於執行使用案例的 Rest API 呼叫排序清單。

使用案例n°1： **建立及部署新的上限設定**

1. list
1. create
1. candeploy
1. deploy

使用案例n°2： **更新並部署尚未部署的上限設定**

1. list
1. get
1. update
1. candeploy
1. deploy

使用案例n°3： **取消部署並刪除已部署的上限設定**

1. list
1. undeploy
1. delete

使用案例n°4： **刪除已部署的上限設定。**

在僅一個 API 呼叫，您可以使用 forceDelete 參數來取消部署和刪除設定。
1. list
1. 刪除，使用 forceDelete 參數

使用案例n°5： **更新已部署的上限設定**

1. list
1. get
1. update
1. undeploy
1. candeploy
1. deploy
