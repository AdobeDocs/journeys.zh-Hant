---
product: adobe campaign
title: 歷程屬性
description: 瞭解行程屬性
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 798e4207-5bef-4002-9c1f-608bb6243e43
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 1%

---

# 行程屬性屬性 {#journey-properties}

在高級表達式編輯器中，您將 **旅程屬性** 類別，位於事件和資料源類別下。 此類別包含與給定配置檔案的行程相關的技術欄位。 這是系統從即時行程中檢索的資訊，如行程ID或遇到的特定錯誤。

>[!NOTE]
>
>簡單表達式編輯器中也提供行程屬性屬性。 查看 [節](../building-journeys/condition-activity.md#about_condition)

![](../assets/journey-properties.png)

您將找到有關以下資訊的資訊：

* 行程版本：行程uid、行程版本uid、實例uid等。
* 錯誤：資料提取、操作執行等。
* 當前步驟、最後當前步驟等。
* 丟棄的配置檔案

您可以使用這些欄位來生成表達式。 在行程執行期間，將直接從行程中檢索這些值。

以下是幾個使用案例的示例：

* **記錄丟棄的配置檔案**:您可以通過封頂規則將消息中排除的所有配置檔案發送到第三方系統以用於日誌記錄。 為此，在超時和出錯時設定路徑，並添加條件以篩選特定錯誤類型，例如：「通過設定上限來放棄人員」。 然後，您可以通過自定義操作將丟棄的配置檔案推送到第三方系統。

* **發送警報以防出錯**:您可以在每次消息出錯時向第三方系統發送通知。 為此，在出錯時設定路徑，添加條件和自定義操作。 例如，您可以在Slack通道上發送通知，並說明遇到的錯誤。

* **改進報告中的錯誤** :您可以為每個錯誤類型定義一個條件，而不是只為出錯消息提供一個路徑。 這將允許您細化報告並查看所有錯誤類型資料。

## 欄位清單 {#journey-properties-fields}

| 類別 | 欄位名稱 | 標籤 | 說明 |
|---|---|---|------------|
| 旅程版本 | 旅程UID | 行程標識符 |  |
|  | journeyVersionUID | 行程版本標識符 |  |
|  | journey版本名 | 行程版本名稱 |  |
|  | journeyVersionDescription | 行程版本說明 |  |
|  | journey版本 | 旅程版本 |  |
| 旅程實例 | 實例UID | 行程實例標識符 | 實例的ID |
|  | 外部密鑰 | 外部密鑰 | 觸發行程的單個標識符 |
|  | 組織ID | 組織標識符 | 品牌組織 |
|  | 沙盒名稱 | 沙盒名稱 | 沙盒的名稱 |
| 身分 | 配置檔案ID | 配置檔案標識符 | 行程中配置檔案的標識符 |
|  | namespace | 配置檔案標識命名空間 | 行程中配置檔案的命名空間(示例：ECID) |
| 當前節點 | 當前節點ID | 當前節點標識符 | 當前活動（節點）的標識符 |
|  | 當前節點名 | 當前節點名稱 | 當前活動（節點）的名稱 |
| 上一個節點 | previousNodeId | 上一個節點標識符 | 上一活動（節點）的標識符 |
|  | previousNodeName | 上一個節點名稱 | 上一活動（節點）的名稱 |
| 錯誤 | lastNodeUIDInError | 錯誤中的最後一個節點標識符 | 錯誤中最新活動（節點）的標識符 |
|  | lastNodeNameInError | 錯誤中的最後一個節點名稱 | 出錯的最新活動（節點）的名稱 |
|  | lastNodeTypeInError | 錯誤中的最後一個節點類型 | 最新活動（節點）的錯誤類型出錯。 可能的類型：<ul><li>事件：Events、Reactions、SQ(示例：細分資格)</li><li>流控制：結束，條件，等待</li><li>操作：ACS操作、跳轉、自定義操作</li></ul> |
|  | 上次錯誤代碼 | 上次錯誤代碼 | 最新活動（節點）的錯誤代碼出錯。 可能的錯誤： <ul><li>HTTP錯誤代碼</li><li>封</li><li>超時</li><li>錯誤(示例：在出現意外錯誤時為預設值。 不應/極少發生)</li></ul> |
|  | 上次執行的ActionErrorCode | 上次執行的操作錯誤代碼 | 錯誤中最新操作的錯誤代碼 |
|  | lastDataFetchErrorCode | 上次資料提取錯誤代碼 | 從資料源獲取最新資料的錯誤代碼 |
| 時間 | lastActionExecutionElapsedTime | 上次操作執行已用時間 | 執行最新操作所花的時間 |
|  | lastDataFetchElapsedTime | 上次資料提取已用時間 | 從資料源執行最新資料提取所花的時間 |
