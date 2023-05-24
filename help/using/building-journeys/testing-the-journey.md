---
product: adobe campaign
title: 測試歷程
description: 瞭解行程測試
feature: Journeys
role: User
level: Intermediate
exl-id: be413905-0631-4229-a954-80a92651206d
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '1576'
ht-degree: 7%

---

# 測試歷程{#testing_the_journey}

在能夠test行程之前，必須解決所有錯誤（如果有）。 請參閱[本節](../about/troubleshooting.md#section_h3q_kqk_fhb)。

您可以在發佈之前使用test配置檔案test您的行程。 這可讓您分析個人在歷程中的流動方式並在發佈前進行疑難排解。

只有測試設定檔才能進入旅程測試模式。您可以建立新的test配置檔案或將現有配置檔案轉換為test配置檔案。 請參閱本[章節](../building-journeys/creating-test-profiles.md)。

要使用test模式，請執行以下步驟：

1. 在測試您的行程之前，請驗證該行程是否有效且無錯誤。 您將無法啟動有錯誤的旅程test。 請參閱[本節](../about/troubleshooting.md#section_h3q_kqk_fhb)。出現錯誤時，將顯示警告符號。

1. 要激活test模式，請按一下 **[!UICONTROL Test]** 切換，位於右上角。

   ![](../assets/journeytest1.png)

1. 使用 **[!UICONTROL Wait time]** 參數，用於定義每個等待活動和事件超時在test模式下持續的時間。 預設時間為等待和事件超時的10秒。 這將確保您快速獲得test結果。 僅當您在行程中丟棄了一個或多個等待活動時，才會顯示此參數。

   ![](../assets/journeytest_wait.png)

   >[!NOTE]
   >
   >在行程中使用超時的反應事件時，等待時間預設值為40秒。 請參閱[本節](../building-journeys/reaction-events.md)。

1. 按一下 **[!UICONTROL Trigger an event]** 配置事件並將事件發送到旅程。

   ![](../assets/journeyuctest1.png)

1. 配置所需的不同欄位。 在 **配置檔案標識符** 欄位，輸入用於標識test配置檔案的欄位值。 例如，它可以是電子郵件地址。 確保發送與test配置檔案相關的事件。 請參閱 [發射事件](#firing_events)。

   ![](../assets/journeyuctest1-bis.png)

1. 收到事件後，按一下 **[!UICONTROL Show log]** 按鈕查看test結果並驗證它們。 請參閱 [查看日誌](#viewing_logs)。

   ![](../assets/journeyuctest2.png)

1. 如果發生任何錯誤，請停用測試模式、修改您的歷程並再次測試。當test確鑿時，你可以發表你的旅程。 請參閱[此頁面](../building-journeys/publishing-the-journey.md)。

## 重要備註 {#important_notes}

* 提供一個介面，用於將事件發射到所測試的旅程，但事件也可以由諸如Postman的第三方系統發送。
* 只允許在即時客戶配置檔案服務中標籤為「test配置檔案」的個人進入測試行程。 請參閱本[章節](../building-journeys/creating-test-profiles.md)。
* test模式僅在使用命名空間的草稿行程中可用。 Test模式需要檢查進入行程的人員是否是test配置檔案，因此必須能夠到達Adobe Experience Platform。
* 在test會話期間，最大可輸入行程的test配置檔案數為100。
* 禁用test模式時，它將從過去或當前已進入該模式的所有人員中清除行程。 它還清除了報告。
* 您可以根據需要多次啟用/禁用test模式。
* 激活test模式時，無法修改行程。 在test模式下，您可以直接發佈行程，無需先前停用test模式。
* 到達分割時，總是選擇頂部分支。 如果希望test選擇其他路徑，則可以重新組織拆分分支的位置。
* 為優化效能並防止過時的資源使用，所有處於test模式且一週內未觸發的行程都將切換回「草稿」狀態。

## 將輪廓轉換為test輪廓{#turning-profile-into-test}

可以將現有配置式轉換為test配置式。 在Adobe Experience Platform，可以通過API調用更新配置檔案屬性，但不能通過介面執行。

最簡單的方法是使用 **更新配置檔案** 操作活動，並將test配置檔案布爾欄位從false更改為true。 請參閱[本節](../building-journeys/update-profiles.md#using-the-test-mode)。

## 建立test配置檔案{#create-test-profile}

如果要建立新的test配置檔案，該過程與在Adobe Experience Platform建立配置檔案時的過程相同。 它通過API調用執行。 查看 [頁](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant)

必須使用包含「配置式test詳細資訊」混合的配置式架構。 testProfile標誌是此混合的一部分。

建立配置檔案時，確保傳遞值：testProfile = true。

請注意，您還可以更新現有配置檔案，以將其testProfile標誌更改為「true」。

下面是建立test配置檔案的API調用示例：

```
curl -X POST \
'https://dcs.adobedc.net/collection/xxxxxxxxxxxxxx' \
-H 'Cache-Control: no-cache' \
-H 'Content-Type: application/json' \
-H 'Postman-Token: xxxxx' \
-H 'cache-control: no-cache' \
-H 'x-api-key: xxxxx' \
-H 'x-gw-ims-org-id: xxxxx' \
-d '{
"header": {
"msgType": "xdmEntityCreate",
"msgId": "xxxxx",
"msgVersion": "xxxxx",
"xactionid":"xxxxx",
"datasetId": "xxxxx",
"imsOrgId": "xxxxx",
"source": {
"name": "Postman"
},
"schemaRef": {
"id": "https://example.adobe.com/mobile/schemas/xxxxx",
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"body": {
"xdmMeta": {
"schemaRef": {
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"xdmEntity": {
"_id": "xxxxx",
"_mobile":{
"ECID": "xxxxx"
},
"testProfile":true
}
}
}'
```

## 發射事件 {#firing_events}

的 **[!UICONTROL Trigger an event]** 按鈕，您可以配置一個事件，使人員進入行程。

>[!NOTE]
>
>在test模式下觸發事件時，將生成一個實事件，這意味著它還會觸發偵聽此事件的其他行程。

作為先決條件，您必須知道哪些配置檔案在Adobe Experience Platform標籤為test配置檔案。 實際上，test模式只允許在行程中使用這些配置檔案，並且事件必須包含ID。 預期ID取決於事件配置。 例如，它可以是ECID或電子郵件地址。 此鍵的值需要添加到 **配置檔案標識符** 的子菜單。

>[!NOTE]
>
>將顯示一個下拉清單，用於預期枚舉的欄位。 只要選擇一個可用的值。

如果您的歷程包含多個事件，請使用下拉式清單選取一個事件。然後，對於每個事件，設定傳遞的欄位和事件傳送的執行。該介面可幫助您在事件負載中傳遞正確的資訊並確保資訊類型正確。 test模式將保存test會話中使用的最後一個參數，以供以後使用。

![](../assets/journeytest4.png)

該介面允許您傳遞簡單事件參數。 如果要傳遞事件中的集合或其他高級對象，可按一下 **[!UICONTROL Code View]** 查看負載的整個代碼並對其進行修改。 例如，您可以複製和貼上由技術用戶準備的事件資訊。

![](../assets/journeytest5.png)

技術用戶也可以使用此介面來合成事件負載和觸發事件，而無需使用第三方工具。

按一下 **[!UICONTROL Send]** 按鈕，test開始。 在行程中個體的進度由視覺流表示。 當個人穿過旅程時，路徑逐漸變綠。 如果發生錯誤，則在相應步驟上顯示警告符號。 您可以將游標置於其上以顯示有關錯誤的詳細資訊並訪問完整詳細資訊（如果可用）。

![](../assets/journeytest6.png)

在事件配置螢幕中選擇其他test配置檔案並再次運行test時，會清除可視流並顯示新個人的路徑。

在test中開啟行程時，顯示的路徑對應於執行的最後一個test。

無論事件是通過介面觸發還是從外部觸發(例如使用Postman)，可視流都有效。

## 基於規則的行程的test模式 {#test-rule-based}

test模式也可用於使用基於規則的事件的行程。 有關基於規則的事件的詳細資訊，請參閱 [此頁](../event/about-events.md)。

觸發事件時， **事件配置** 螢幕允許您定義要在test中傳遞的事件參數。 通過按一下右上角的工具提示表徵圖，可以查看事件ID條件。 每個屬於規則評估的欄位旁邊也提供工具提示。

![](../assets/alpha-event8.png)

有關如何使用test模式的詳細資訊，請參閱 [此頁](../building-journeys/testing-the-journey.md)。

## 查看日誌 {#viewing_logs}

的 **[!UICONTROL Show log]** 按鈕來查看test結果。 此頁以JSON格式顯示行程的當前資訊。 一個按鈕允許您複製整個節點。 您需要手動刷新頁面以更新行程的test結果。

![](../assets/journeytest3.png)

>[!NOTE]
>
>在test日誌中，如果調用第三方系統（資料源或操作）時出錯，則顯示錯誤代碼和錯誤響應。

此時將顯示當前旅程中的個人（技術上稱為實例）數。 下面是為每個人顯示的有用資訊：

* _ID_:旅途中個人的內部身份。 這可用於調試。
* _當前步驟_:個體在旅途中的步驟。 我們建議將標籤添加到您的活動中，以便更輕鬆地識別它們。
* _當前步驟_ >階段：個人行程的狀態（正在運行、已完成、錯誤或超時）。 請參閱下方以了解更多資訊。
* _當前步驟_ > _額外資訊_:錯誤和其他上下文資訊的說明。
* _當前步驟_ > _提取錯誤_:有關此步驟期間發生的讀取資料錯誤的資訊。
* _外部鍵_:在事件中定義的鍵公式的值。
* _豐富的資料_:行程使用資料源時已檢索到的資料。
* _過渡歷史_:個人遵循的步驟清單。 對於事件，將顯示負載。
* _actionExecutionErrors_ :錯誤資訊。

以下是個人旅程的不同狀態：

* _正在運行_:這個人正在旅行中。
* _已完成_:這個人在旅程的終點。
* _錯誤_:由於錯誤，個人在旅途中被停止。
* _超時_:在旅途中，由於一個步驟花了太多時間，個人被攔住了。

當使用test模式觸發事件時，使用源的名稱自動生成資料集。

當使用test模式觸發事件時，使用源的名稱自動生成資料集。

test模式會自動建立「體驗事件」並將其發送到Adobe Experience Platform。 此體驗事件的源名稱為「Journey OrchestrationTest事件」。
