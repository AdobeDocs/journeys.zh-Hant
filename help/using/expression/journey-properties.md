---
product: adobe campaign
title: 歷程屬性
description: 瞭解歷程屬性
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 798e4207-5bef-4002-9c1f-608bb6243e43
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 3%

---

# 歷程屬性屬性 {#journey-properties}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 按兩下這裡[&#128279;](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}以取得Journey Optimizer 檔。
>
>
>_本檔涉及已被Journey Optimizer 取代的舊版Journey Orchestration資料。 如果您對 Journey Orchestration 或 Journey Optimizer 的訪問許可權有疑問，請連絡您的帳戶團隊。_


在進階運算式編輯者中，您將在事件和資料來源類別下方找到 **類別旅程屬性** 。 此類別包含與給定設定檔的旅程相關的技術欄位。 這是系統從即時旅程中檢索的資訊，例如旅程ID或遇到的特定錯誤。

>[!NOTE]
>
>歷程屬性屬性也可在簡單運算式編輯者中使用。 請參閱本[章節](../building-journeys/condition-activity.md#about_condition)

![](../assets/journey-properties.png)

您會找到下列資訊，例如：

* 歷程版本：歷程uid、歷程版本uid、執行個體uid等。
* 錯誤：資料擷取、動作執行等。
* 目前步驟、上一個目前步驟等。
* 捨棄的設定檔

您可以使用這些欄位來建立運算式。 在歷程執行期間，值將直接從歷程中擷取。

以下是一些使用案例的範例：

* **記錄捨棄的設定檔**：您可以傳送上限規則從訊息中排除的所有設定檔至協力廠商系統，以進行記錄。 為此，您可以設定發生逾時和錯誤時的路徑，並新增條件以篩選特定錯誤型別，例如：「藉由上限規則來捨棄人員」。 接著，您就可以透過自訂動作，將捨棄的設定檔推送至協力廠商系統。

* **發生錯誤時傳送警示**：每次訊息發生錯誤時，您都可以傳送通知給協力廠商系統。 您可以針對此專案設定路徑，以預防發生錯誤、新增條件和自訂動作。 例如，您可以在Slack頻道上傳送通知，並附上所遇到錯誤的說明。

* **調整報告中的錯誤** ：您可以針對每個錯誤型別定義條件，而不只是讓一個路徑存放錯誤的訊息。 這可讓您調整報告並檢視所有錯誤型別資料。

## 欄位清單 {#journey-properties-fields}

| 類別 | 欄位名稱 | 標籤 | 說明 |
|---|---|---|------------|
| 歷程版本 | journeyUID | 歷程識別碼 | |
| | journeyVersionUID | 歷程版本識別碼 | |
| | journeyVersionName | 歷程版本名稱 | |
| | journeyVersionDescription | 歷程版本說明 | |
| | journeyVersion | 歷程版本 | |
| 歷程執行個體 | instanceUID | 歷程執行個體識別碼 | 執行個體的ID |
| | externalKey | 外部金鑰 | 觸發歷程的個別識別碼 |
| | organizationId | 組織識別碼 | 品牌的組織 |
| | sandboxName | 沙箱名稱 | 沙箱的名稱 |
| 身分識別 | profileId | 設定檔識別碼 | 歷程中設定檔的識別碼 |
| | 名稱空間 | 設定檔身分名稱空間 | 歷程中設定檔的名稱空間（範例：ECID） |
| 目前節點 | currentNodeId | 目前的節點識別碼 | 目前活動的識別符 （節點） |
| | currentNodeName | 目前節點名稱 | 目前活動的名稱 （節點） |
| 上一個節點 | previousNodeId | 上一個節點標識符 | 先前活動的識別符 （節點） |
| | previousNodeName | 前一個節點名稱 | 上一個活動的名稱（節點） |
| 錯誤 | lastNodeUIDInError | 最後一個錯誤的節點識別碼 | 最新錯誤活動（節點）的識別碼 |
| | lastNodeNameInError | 最後一個錯誤的節點名稱 | 發生錯誤的最新活動（節點）的名稱 |
| | lastNodeTypeInError | 最後一個錯誤的節點型別 | 發生錯誤的最新活動（節點）的錯誤型別。 可能的型別：<ul><li>事件：事件、回應、SQ （範例：區段資格）</li><li>流量控制：結束、條件、等待</li><li>動作：ACS動作、跳轉、自訂動作</li></ul> |
| | lastErrorCode | 上一錯誤碼 | 最新錯誤活動（節點）的錯誤代碼。 可能的錯誤： <ul><li>HTTP錯誤碼</li><li>上限</li><li>timedOut</li><li>錯誤(範例：發生意外錯誤時的預設。 不應/極少數發生)</li></ul> |
| | lastExecutedActionErrorCode | 上次執行動作 錯誤 Code | 錯誤錯誤的最新動作的程序代碼 |
| | lastDataFetchErrorCode | 上次資料擷取的錯誤碼 | 從資料來源擷取的最新資料之錯誤代碼 |
| 時間 | lastActionExecutionElapsedTime | 執行最後一個動作經過的時間 | 執行最新動作所花費的時間 |
| | lastDataFetchElapsedTime | 擷取上次資料經過的時間 | 從資料來源執行最新資料擷取所花的時間 |
