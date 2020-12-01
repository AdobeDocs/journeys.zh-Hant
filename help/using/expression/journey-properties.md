---
product: adobe campaign
solution: Journey Orchestration
title: 歷程屬性
description: 瞭解歷程屬性
translation-type: tm+mt
source-git-commit: 341138c31676870878099b4f4eecec200a614c69
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 0%

---


# 旅程屬性{#journey-properties}

在進階運算式編輯器中，您會在事件與資料來源類別下方找到&#x200B;**歷程屬性**&#x200B;類別。 此類別包含與特定描述檔之旅程相關的技術欄位。 這是系統從即時歷程擷取的資訊，例如歷程ID或遇到的特定錯誤。

![](../assets/journey-properties.png)

您將會找到有關以下內容的資訊：

* 歷程版本：journey uid、journey version uid、instance uid等。
* 錯誤：資料擷取、動作執行等。
* 當前步驟、最後一個當前步驟等。
* 捨棄的描述檔

您可以使用這些欄位來建立運算式。 在行程執行期間，將直接從行程中擷取值。

以下是一些使用案例的範例：

* **記錄已放棄的配置檔案**:您可以透過封閉規則，將所有已排除在訊息之外的描述檔傳送至第三方系統，以便進行記錄。為此，您可以在逾時和錯誤的情況下設定路徑，並新增條件以篩選特定錯誤類型，例如：「封閉規則以捨棄人」。 然後，您可以透過自訂動作將已捨棄的描述檔推送至協力廠商系統。

* **在發生錯誤時傳送警報**:您可以在每次訊息發生錯誤時，傳送通知給第三方系統。為此，您可以設定路徑以防發生錯誤，新增條件和自訂動作。 例如，您可以在Slack頻道上傳送通知，並說明所遇到的錯誤。

* **調整報表中的錯誤** :您可以針對錯誤類型定義條件，而不是只有一條錯誤訊息路徑。這可讓您調整報表並檢視所有錯誤類型資料。

## 欄位清單{#journey-properties-fields}

| 類別 | 欄位名稱 | 標籤 | 說明 |
|---|---|---|------------|
| 歷程版本 | journeyUID | 歷程識別碼 |  |
|  | journeyVersionUID | 歷程版本識別碼 |  |
|  | journeyVersionName | 歷程版本名稱 |  |
|  | journeyVersionDescription | 歷程版本說明 |  |
|  | journeyVersion | 歷程版本 |  |
| 歷程例項 | instanceUID | 歷程例項識別碼 | 實例的ID |
|  | externalKey | 外部鍵 | 觸發歷程的個別識別碼 |
| 身份 | profileId | 描述檔識別碼 | 旅程中描述檔的識別碼 |
|  | namespace | 描述檔識別名稱空間 | 歷程中描述檔的命名空間(範例：ECID) |
| 當前節點 | currentNodeId | 當前節點標識符 | 當前活動（節點）的標識符 |
|  | currentNodeName | 當前節點名稱 | 當前活動（節點）的名稱 |
| 上一個節點 | previousNodeId | 上一個節點標識符 | 先前活動（節點）的識別碼 |
|  | previousNodeName | 上一個節點名稱 | 上一個活動（節點）的名稱 |
| 錯誤 | lastNodeUIDInError | 錯誤中的最後一個節點標識符 | 錯誤中最新活動（節點）的標識符 |
|  | lastNodeNameInError | 錯誤的最後一個節點名稱 | 錯誤的最新活動（節點）的名稱 |
|  | lastNodeTypeInError | 錯誤的最後一個節點類型 | 錯誤中最新活動（節點）的錯誤類型。 可能的類型：<ul><li>事件：事件、反應、SQ(例如：區段資格)</li><li>流量控制：結束、條件、等待</li><li>動作：ACS動作、跳轉、自訂動作</li></ul> |
|  | lastErrorCode | 上次錯誤代碼 | 錯誤中最新活動（節點）的錯誤代碼。 可能的錯誤： <ul><li>HTTP錯誤代碼</li><li>限制</li><li>timedOut</li><li>錯誤(範例：預設值，以避免發生意外錯誤。 不應／極少發生)</li></ul> |
|  | lastExecutedActionErrorCode | 上次執行的動作錯誤代碼 | 錯誤中最新動作的錯誤代碼 |
|  | lastDataFetchErrorCode | 上次資料獲取錯誤代碼 | 從資料來源擷取最新資料的錯誤碼 |
| 時間 | lastActionExecutionElapsedTime | 上次動作執行已用時間 | 執行最新動作所花的時間 |
|  | lastDataFetchElapsedTime | 上次資料獲取用時 | 從資料來源擷取最新資料所花的時間 |
