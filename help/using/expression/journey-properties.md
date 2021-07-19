---
product: adobe campaign
title: 歷程屬性
description: 了解歷程屬性
feature: 歷程
role: Data Engineer
level: Experienced
exl-id: 798e4207-5bef-4002-9c1f-608bb6243e43
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 1%

---

# 歷程屬性屬性 {#journey-properties}

在進階運算式編輯器中，您會在事件和資料來源類別下方找到&#x200B;**歷程屬性**&#x200B;類別。 此類別包含指定設定檔之歷程的相關技術欄位。 這是系統從即時歷程擷取的資訊，例如歷程ID或遇到的特定錯誤。

>[!NOTE]
>
>簡單運算式編輯器中也提供歷程屬性。 請參閱此[節](../building-journeys/condition-activity.md#about_condition)

![](../assets/journey-properties.png)

您會找到以下相關資訊：

* 歷程版本：journey uid、journey version uid、instance uid等
* 錯誤：資料擷取、動作執行等。
* 目前步驟、最後一個目前步驟等。
* 捨棄的設定檔

您可以使用這些欄位來建立運算式。 在歷程執行期間，會直接從歷程擷取值。

以下是幾個使用案例的範例：

* **記錄捨棄的設定檔**:您可以將限定規則從訊息中排除的所有設定檔傳送至協力廠商系統，以用於記錄用途。針對此，您可在逾時和錯誤的情況下設定路徑，並新增條件以篩選特定錯誤類型，例如：「借由限定規則捨棄使用者」。 然後，您可以透過自訂動作將已捨棄的設定檔推送至協力廠商系統。

* **發生錯誤時傳送警報**:您可以在每次訊息發生錯誤時，傳送通知給協力廠商系統。針對此，您可以設定路徑以防發生錯誤，然後新增條件和自訂動作。 例如，您可以在Slack通道上傳送通知，並說明遇到的錯誤。

* **調整報表中的錯誤** :您可以針對每個錯誤類型定義條件，而不是只有一條錯誤訊息路徑。這可讓您調整報表並檢視所有錯誤類型資料。

## 欄位清單 {#journey-properties-fields}

| 類別 | 欄位名稱 | 標籤 | 說明 |
|---|---|---|------------|
| 歷程版本 | journeyUID | 歷程識別碼 |  |
|  | journeyVersionUID | 歷程版本識別碼 |  |
|  | journeyVersionName | 歷程版本名稱 |  |
|  | journeyVersionDescription | 歷程版本說明 |  |
|  | journeyVersion | 歷程版本 |  |
| 歷程例項 | instanceUID | 歷程例項識別碼 | 例項ID |
|  | externalKey | 外部密鑰 | 觸發歷程的個別識別碼 |
|  | organizationId | 組織識別碼 | 品牌組織 |
|  | sandboxName | 沙箱名稱 | 沙箱名稱 |
| 身分 | profileId | 設定檔身分識別碼 | 歷程中的設定檔識別碼 |
|  | namespace | 設定檔身分命名空間 | 歷程中設定檔的命名空間(範例：ECID) |
| 當前節點 | currentNodeId | 當前節點標識符 | 當前活動（節點）的標識符 |
|  | currentNodeName | 當前節點名稱 | 當前活動的名稱（節點） |
| 上一節點 | previousNodeId | 上一個節點標識符 | 前一個活動（節點）的標識符 |
|  | previousNodeName | 上一個節點名稱 | 上一個活動（節點）的名稱 |
| 錯誤 | lastNodeUIDInError | 最後一個節點標識符出錯 | 最新活動（節點）的標識符出錯 |
|  | lastNodeNameInError | 錯誤中的最後一個節點名稱 | 最新活動（節點）的名稱出錯 |
|  | lastNodeTypeInError | 錯誤中的最後一個節點類型 | 錯誤中最新活動（節點）的錯誤類型。 可能的類型：<ul><li>事件：事件、反應、SQ(示例：區段資格)</li><li>流量控制：結束，條件，等待</li><li>動作：ACS操作，跳轉，自定義操作</li></ul> |
|  | lastErrorCode | 上次錯誤代碼 | 最新活動（節點）的錯誤代碼。 可能的錯誤： <ul><li>HTTP錯誤代碼</li><li>限制</li><li>timedOut</li><li>錯誤(範例：預設值，以備發生非預期錯誤時使用。 不應/極少發生)</li></ul> |
|  | lastExecutedActionErrorCode | 上次執行的動作錯誤碼 | 最新動作的錯誤碼 |
|  | lastDataFetchErrorCode | 上次資料擷取錯誤代碼 | 從資料來源擷取最新資料的錯誤碼 |
| 時間 | lastActionExecutionElapsedTime | 上次操作執行已用時間 | 執行最新動作的逗留時間 |
|  | lastDataFetchElapsedTime | 上次資料擷取間隔時間 | 從資料來源執行最新資料擷取的逗留時間 |
