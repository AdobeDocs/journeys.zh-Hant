---
product: adobe campaign
title: 版本注意事項
description: 瞭解發行說明
feature: Journeys
role: User
level: Beginner
exl-id: b923f7e3-997b-483b-b6ac-eef62fc81a84
source-git-commit: 0d1355f036b22df6b484ed2a0ea9a8b121e947e0
workflow-type: tm+mt
source-wordcount: '3164'
ht-degree: 64%

---

# 版本注意事項 {#release-notes}

本頁面列出 Journey Orchestration 的所有新功能和改善項目。
您也可以參閱最新的[文件更新](../release-notes/documentation-updates.md)。

## 2022 年 2 月發行 {#february-2022-release}

### 改進項目

* 為優化效能並防止過時的資源使用，所有處於test模式且一週內未觸發的行程現在將切換回「草稿」狀態。 [閱讀全文](../building-journeys/testing-the-journey.md#important_notes)

## 2022 年 1 月發行版本 {#january-2022-release}

### 改進項目

* Journey Orchestration步驟事件現在可以連結到中的其他資料集 [AdobeCustomer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hant)。  內建「歷程步驟事件」方案中的 **profileID** 欄位現在定義為身分欄位。 [了解更多](../building-journeys/sharing-overview.md#integration-cja)
* Adobe Campaign Standard操作的上限規則已更改為4000次呼叫/5分鐘。 [閱讀全文](../action/working-with-adobe-campaign.md)

## 2021 年 10 月發行版本 {#october-2021-release}

### 改進項目

* **運算式編輯器**  - 身為超級使用者，您現在可以使用函式來處理地圖。 [了解更多](../expression/field-references.md)
* **輔助功能**  — 已實施輔助功能增強。 Journey Orchestration現在在可訪問性方面完全符合。
* **集合**  - 現在支援包含子物件的物件陣列。 [閱讀全文](../usecase/collections.md)
* **監控**  - 已增強即時歷程和測試模式的步驟事件。 [新欄位](../building-journeys/sharing-field-list.md#serviceevents) 已新增與設定檔匯出作業有關的內容。 為了獲得更好的用戶體驗，現在將步驟事件欄位組織在行程步驟事件架構中的不同類別中以進行Journey Orchestration。 所有先前的步驟事件欄位仍可在 [stepEvents](../building-journeys/sharing-legacy-fields.md) 類別中使用。

## 2021 年 9 月發行版本 {#september-2021-release}

<table>
<thead>
<tr>
<th><strong>使用自訂動作以動態方式傳遞資料清單</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>您現在可以在自訂動作參數中傳遞集合或資料清單，這些參數將在執行階段以動態方式填入。 支援兩種集合：簡單集合和物件集合。 先前建立的自訂動作將可繼續運作。 </p>
<p>如需關於集合的詳細資訊，請參閱<a href="../usecase/collections.md">詳細文件</a>。 </p>
<p>篩選和交集函式已在進階運算式編輯器中加入可用函式清單。 這提供了更多可能性來篩選和比較集合。</p>
<p>請參閱<a href="../functions/functionfilter.md">篩選</a>和<a href="../functions/functionintersect.md">交集</a>函式。</p>
</td>
</tr>
</tbody>
</table>

### 改進項目

* 在佈建步驟事件期間建立並由系統產生的方案和資料集現在改為唯讀模式，可避免重要方案發生任何意外修改。 [進一步了解](../building-journeys/sharing-overview.md)
* 簡潔標示&#x200B;**等待**&#x200B;活動，並在畫布中顯示標籤。 標籤也會用於報告和測試模式記錄，以清楚識別您正在執行的動作。 [進一步了解](../building-journeys/using-the-journey-designer.md)
* 使用搜尋，透過篩選&#x200B;**事件**&#x200B;和&#x200B;**動作**&#x200B;類別中的元素，更快找到您的事件和動作。 不再篩選協調活動。 [進一步了解](../building-journeys/using-the-journey-designer.md)
* 在基於規則中定義事件ID條件時，「contains」運算子現在可用於欄位的字串類型。 [進一步了解](../event/about-creating.md)

## 2021 年 8 月發行版本 {#august-2021-release}

### 改進項目

**歷程**

* **動態標頭** - 您現在可以在 HTTP 標頭參數中傳遞動態資料。 接收歷程動作 HTTP 呼叫的整合系統可使用這些參數 (例如時間戳記或追蹤 ID)。 [閱讀全文](../action/url-configuration.md)
* **Dynamic URL 路徑** - 您現在可以為自訂動作設定動態 URL 路徑。 [閱讀全文](../action/url-configuration.md)

## 2021 年 7 月發行版本 {#july-2021-release}

<table>
<thead>
<tr>
<th><strong>利用結構描述關係</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform允許定義架構之間的關係，以便將一個資料集用作另一個資料集的查找表。 Journey Orchestration現在可以利用來自連結架構的資料。</p>
<p>這些欄位在單一事件配置、行程條件和自定義操作個性化中可用。
<p>如需詳細資訊，請參閱<a href="../event/experience-event-schema.md#leverage_schema_relationships">詳細文件</a>。</p>
</td>
</tr>
</tbody>
</table>

### 改進項目

* **快取期間** 欄位已從資料來源設定窗格中移除。 [閱讀全文](../datasource/about-data-sources.md)

## 2021 年 6 月發行 {#june-2021-release}

<table>
<thead>
<tr>
<th><strong> Adobe Campaign Classic整合</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>與Adobe Campaign Classic一體化的一體化現已正式啟動。 它允許您使用Adobe Campaignv7或v8事務性消息傳遞功能發送電子郵件、推送通知和SMS。</p>
<p>Journey Orchestration 與 Campaign 執行個體之間的連線在佈建時由 Adobe 設定。</p>
<p>如需詳細資訊，請參閱<a href="../action/acc-action.md">詳細文件</a>。</p>
</td>
</tr>
</tbody>
</table>

### 改進項目

* 對於外部資料來源，現在會自動定義每秒 15 次呼叫的上限規則。 [閱讀全文](../about/external-systems.md#capping)
* 簡單和高級表達式編輯器現在支援XDM日期格式。
* 在行程清單螢幕中，已添加新篩選器。 您現在可以按行程類型篩選： **[!UICONTROL Unitary event]** 或 **[!UICONTROL Segment qualification]**。 [閱讀全文](../about/user-interface.md#section_lgm_hpz_pgb)
* 對於即時歷程，歷程屬性畫面現在會顯示發佈日期和發佈歷程的使用者名稱。 當您複製行程的技術詳細資訊時，也可以獲得此資訊。 [閱讀全文](../building-journeys/changing-properties.md#section_lgm_hpz_pgb)

## 2021 年 4 月發行 {#april-2021-release}

### 改進項目

* 在 **事件配置** 在test模式的螢幕中，現在將顯示一個下拉清單，用於預期枚舉的欄位。 只需選擇一個可用值。 如果定義了錯誤值，則在觸發事件時將避免出錯。 [閱讀全文](../building-journeys/testing-the-journey.md#firing_events)

## 2021 年 3 月發行 {#march-2021-release}

### 改進項目

* 已將新狀態添加到旅程。 行程結束或手動關閉時，其狀態將從 **已關閉** 至 **已完成** 關閉30天後。 這樣，您就可以更輕鬆地識別不活動的行程，同時確保所有在場人員有時間完成行程。 [閱讀全文](../building-journeys/journey.md#ending_a_journey)
* 在草稿乘程的活動右窗格中，只讀欄位現在預設為隱藏。 這種介面簡化將幫助您更輕鬆地配置活動。 要顯示它們，請按一下 **顯示只讀欄位** 表徵圖，可在活動配置窗格的左上角使用。 [閱讀全文](../building-journeys/using-the-journey-designer.md#configuration_pane)
* 在test模式下，在 **事件配置** 螢幕， **鍵** 用於定義test配置檔案ID的欄位已更名 **配置檔案標識符** 獲得更好的用戶體驗。 [閱讀全文](../building-journeys/testing-the-journey.md)。
* 對於反應事件，現在只能將超時持續時間設定在40秒到30天之間。 測試使用反應事件的行程時，test模式 **[!UICONTROL Wait time]** 預設值和最小值現在為40秒。 [閱讀全文](../building-journeys/reaction-events.md)。

## 2021 年 2 月發行 {#february-2021-release}

<table>
<thead>
<tr>
<th><strong>更新配置檔案活動</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>此新操作活動允許您使用來自事件、資料源或使用特定值的資訊更新現有Adobe Experience Platform配置檔案。</p>
<p>如需詳細資訊，請參閱<a href="../building-journeys/update-profiles.md">詳細文件</a>。</p>
</td>
</tr>
</tbody>
</table>

### 其他改善項目

* 現在，配置事件時，預設情況下只會預選XDM驗證所必需的欄位。 無法取消選擇這些欄位。
* 在行程調色板中，已添加新篩選器。 它允許您僅顯示使用的前五個事件和操作，以及現成的事件和操作。 這特定於每個用戶。 預設情況下，將顯示所有項目。 [閱讀全文](../building-journeys/using-the-journey-designer.md#palette)
* 開始新行程時，無法作為第一步放入畫布中的元素現在將隱藏。 這涉及所有操作、條件活動、等待和反應。
* 在高級表達式編輯器的左側部分，函式現在在 **函式** 清單中。

## 2021 年 1 月發行 {#january-2021-release}

在事件配置中選擇架構時，只選擇Journey Orchestration正確接收事件所必需的欄位。 [閱讀全文](../event/defining-the-payload-fields.md)

行程屬性屬性現在可在簡單表達式編輯器中使用。 [閱讀全文](../expression/journey-properties.md)

添加了兩個新的行程屬性屬性（sandboxName和organizationId）。 [閱讀全文](../expression/journey-properties.md)

為了與Adobe Campaign StandardSLA保持一致，一旦建立Adobe Campaign Standard整合，現在將自動為Adobe Campaign Standard行動定義每秒13次呼叫的上限規則。 [閱讀全文](../action/working-with-adobe-campaign.md)

事件超時持續時間現在在超時路徑上被更清楚地指定。 [閱讀全文](../building-journeys/event-activities.md#listening-to-events-during-a-specific-time)

的 [getListItem](../functions/functiongetlistitem.md) 和 [分裂](../functions/functionsplit.md) 函式已添加到高級表達式編輯器中可用的函式清單中。 這將為字串計算使用情形提供更多可能性。

## 2020 年 11 月發行版本 {#november-release}

<table>
<thead>
<tr>
<th><strong>從一個歷程跳到另一個歷程</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新的活動允許您將個人從一個行程推送到另一個行程。 的 <strong>跳</strong> 活動允許您：
</p>
<ul>
<li>將複雜旅程分成若干個，簡化其設計 </li>
<li>基於常用和可重複使用的行程模式構建行程</li>
</ul>
<p>有關詳細資訊，請參閱 <a href="../building-journeys/jump.md">詳細文檔</a> 和 <a href="https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html?lang=zh-Hant">教程視頻</a>。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>在表達式編輯器中使用行程屬性</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>在高級表達式編輯器中，我們在欄位和函式清單中添加了一個新類別。 這是系統從即時行程中檢索的資訊，如行程ID或遇到的特定錯誤。 這樣你在旅途中就會有更多機會。 例如，如果在條件或操作中遇到錯誤，您將能夠向第三方系統發出警報。
</p>
<p>如需詳細資訊，請參閱<a href="../expression/journey-properties.md">相關的文件</a>，以瞭解詳情。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>規則型事件 (β)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>現在可使用一種新方法來更輕鬆地設定事件，而無需使用eventID:基於規則的事件根據條件評估是否應觸發該事件。 您仍然可以使用現有方法，現在稱為「系統生成」。 這一功能已通過Alpha計畫在有限的客戶群中測試過，現在已面向所有客戶提供Beta版。
</p>
</td>
</tr>
</tbody>
</table>

### 其他改善項目

建立新版本的旅程時增加了限制。 這些限制避免了過於劇烈的變化，使版本之間保持一定的一致性。 [閱讀全文](../about/limitations.md#journey-versions-limitations)

的 **段資格** 活動不再能用於包含Campaign Standard消息活動的旅程。 此限制保護Adobe Campaign Standard實例的完整性。 事實上，使用段資格可能會導致每天消息發送高峰，使Campaign Standard事務性消息過載。 [閱讀全文](../about/limitations.md#segment-qualification)

## 2020 年 10 月發行版本 {#october-release}

<table>
<thead>
<tr>
<th><strong>事件超時</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>現在，您可以為事件配置超時，以便僅在特定時間內進行行程偵聽事件。 您不再需要在事件路徑上並行添加等待活動來實現此目標。
</p>
<p>如需詳細資訊，請參閱<a href="../building-journeys/event-activities.md#listening-to-events-during-a-specific-time">詳細文件</a>。</p>
</td>
</tr>
</tbody>
</table>

### 其他改善項目

* 當您發佈新版本的行程時，舊版本將自動結束並切換到「已關閉」狀態。 [閱讀全文](../building-journeys/journey-versions.md)

## 2020 年 9 月發行版本 {#september-release}

### GA 更新{#september-ga-update}

<table>
<thead>
<tr>
<th><strong>條件活動改進</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>在將條件添加到行程時，您現在可以定義標籤。 如果在旅途中使用多個條件，則可以更輕鬆地識別它們。
</p>
<p>如需詳細資訊，請參閱<a href="../building-journeys/condition-activity.md#about_condition">詳細文件</a>。</p>
</td>
</tr>
</tbody>
</table>

### Alpha 更新{#september-alpha-update}

<table>
<thead>
<tr>
<th><strong>讀取段活動改進</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>以下對 <strong>讀取段</strong> 活動：
</p>
<ul>
<li><p>現在，基於段的行程顯示在畫布上方，提醒您行程的日程類型。 您可以按一下此提醒以訪問計畫配置菜單。</p>
</li>
<li><p>已改進test模式日誌的粒度以顯示段導出進度狀態。</p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

## 2020 年 8 月發行版本 {#august-release}

### GA 更新{#august-ga-update}

「區段資格」事件的裝載現在包含下列內容資訊，您可在條件和動作中使用：行為（入口、出口）、資格的時間戳記及區段 ID。[閱讀全文](../building-journeys/segment-qualification-events.md)

### Alpha 更新{#august-alpha-update}

<table>
<thead>
<tr>
<th><strong>區段觸發器活動</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>已對「區段觸發器」活動進行下列改良：
</p>
<ul>
<li><p>活動的名稱已變更為「閱讀區段」。 </p>
</li>
<li><p>已從活動屬性移除歷程排程器的設定。現在可直接從「歷程」的屬性存取，在專用區段中，將「閱讀區段」活動拖曳至畫布時，其就會顯示。 </p>
</li>
<li><p>您現在可以在單一設定檔上測試歷程，並使用視覺流量追蹤歷程的進度。</p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>規則型事件</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>已對規則型事件進行下列改良：
</p>
<ul>
<li><p>您現在可以運用您已擷取並串流至 Platform 的所有 Adobe Analytics 行為事件資料，以觸發歷程並自動化客戶體驗。<a href="../event/about-analytics.md">閱讀全文</a></p>
</li>
<li><p>在測試模式中觸發規則型事件時，您現在可以直接檢視事件 ID 條件。此外，規則評估的每個欄位旁都已新增工具提示。<a href="../building-journeys/testing-the-journey.md#test-rule-based">閱讀全文</a></p>
</li>
<li><p>規則型事件定義畫面已重新整理，進而改善體驗。<a href="../event/about-creating.md">閱讀全文</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

## Alpha 版- 2020 年 7 月 {#alpha-release---july-2020}

Alpha 方案提供目前在有限客戶群中進行測試的功能。這可讓我們根據收到的意見回饋來改良產品。並非所有 Journey Orchestration 客戶都能使用這些功能。

<table>
<thead>
<tr>
<th><strong>增強的使用者介面</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>為了提供與 Adobe Experience Platform 一致的介面，已增強 Journey Orchestration 功能表中的導覽功能：
</p>
<ul>
<li><p>已將功能表從介面的上方移至左側。 </p>
</li>
<li><p>將管理功能分組至單一儀表板。</p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>區段觸發器活動</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>「區段觸發」活動可讓您將屬於 Adobe Experience Platform 區段的所有個人進入歷程。進入歷程可以執行一次，也可以定期執行。 
</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>規則型事件</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>我們已簡化設定 Experience 事件的方式。我們將推出不需要使用 eventID 的新方法。當您在 Journey Orchestration 中設定事件時，現在可以定義規則型活動。<a href="../event/about-events.md">閱讀全文</a>
</p>
</td>
</tr>
</tbody>
</table>


## 第 2 季度發行 - 2020 年 6 月 {#q2-release---june-2020}

<table>
<thead>
<tr>
<th><strong>Adobe Experience Platform 整合增強功能</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>已進行下列 Adobe Experience Platform 整合增強功能：</p>
<ul>
<li><p>新活動可監聽 Adobe Experience Platform 區段入口/出口，以便讓人員進入歷程或是在歷程中前進。<a href="../building-journeys/segment-qualification-events.md">閱讀全文</a></p>
<img src="../assets/rn-segment7.png"/>
</li>
<li><p>由於新的 <strong>Segments</strong> 索引標籤，現在無需離開 Journey Orchestration 介面，即可建立及編輯 Adobe Experience Platform 區段。<a href="../segment/about-segments.md">閱讀全文</a></p>
<img src="../assets/rn-segment1.png"/>
</li>
<li><p>在簡單運算式編輯器中，Adobe Experience Platform 區段現在會直接列在導覽樹狀結構中，以方便設定 "does this person belong to segment A?" 等條件。<a href="../segment/using-a-segment.md">閱讀全文</a></p>
<img src="../assets/rn-segment4.png"/>
</li>
<li><p>Journey Orchestration 現在會自動傳遞至 Adobe Experience Platform，在歷程中執行的步驟。這包含可能發生的錯誤。可藉由針對特定歷程或所有歷程的 Journey Step 事件執行查詢，而將此資訊用於實現報告及疑難排解。<a href="../building-journeys/sharing-overview.md">閱讀全文</a></p>
<img src="../assets/rn-journeystepevent.png"/>
</li>
<li><p>現在可將 Journey Orchestration 連線至生產及非生產 Adobe Experience Platform 沙箱。請注意，沙箱是測試版功能。<a href="../about/access-management.md#sandboxes">閱讀全文</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>歷程設計程式與測試模式增強功能</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>已對歷程設計程式和測試模式進行下列增強功能：</p>
<ul>
<li><p>您現在可以選取 1 或 N 個歷程活動，而在歷程之間複製和貼上活動。<a href="../building-journeys/using-the-journey-designer.md#copy-paste">閱讀全文</a></p>
<img src="../assets/rn-copy-paste1.png"/>
</li>
<li><p>在觸發事件而讓測試設定檔進入歷程後，您現在可以透過彩色視覺流程，而瞭解其在歷程中的進度。在歷程中發生錯誤時，也會顯示錯誤的詳細資料。<a href="../building-journeys/testing-the-journey.md#firing_events">閱讀全文</a></p>
<img src="../assets/rn-journeytest6.png"/>
</li>
<li>已將 <strong>Finished</strong> 歷程重新命名為 <strong>Closed (no entrance)</strong>，以便更妥善地反映此狀態代表的意義。</li>
</ul>
</td>
</tr>
</tbody>
</table>

**其他改善項目**

為了避免傳送過多 API 呼叫至協力廠商系統，我們推出新的公用 API 來設定 &quot;capping&quot; 規則。上限規則可定義每毫秒對 API 端點的呼叫數量上限。[閱讀全文](../api/capping.md)

存取控制現在可以更精細地管理使用者的存取權限。生效日期：2020 年 6 月 30 日。[閱讀全文](../about/access-management.md#create-product-profile)

Journey Orchestration 現在已於 APAC（澳洲資料中心）推出。生效日期：2020 年 6 月 30 日

Journey Orchestration　介面提供日文版。

## 第 1 季發行 - 2020 年 3 月 {#q1-release---march-2020}

<table>
<thead>
<tr>
<th><strong>測試模式增強功能</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>測試模式已進行下列增強：</p>
<ul>
<li>如果歷程使用數個事件，您現在可以在測試模式的<strong>「事件設定」</strong>畫面中，從下拉式清單中個別觸發每個事件。<a href="../building-journeys/testing-the-journey.md#firing_events">閱讀全文</a></p></li>
<li><p>如果歷程中使用一或多個<strong>「等待」</strong>活動，您現在可以定義每個活動在測試模式中的持續時間。預設時間為 10 秒。您可以使用左下角的<strong>「測試等待時間」</strong>參數來變更此項目。<a href="../building-journeys/testing-the-journey.md">閱讀全文</a></p><img src="../assets/rn-test.png"/>
</li>
<li>在<strong>測試記錄</strong>中，如果在呼叫協力廠商系統 (資料來源或動作) 時發生錯誤，現在會顯示錯誤代碼和錯誤回應。<a href="../building-journeys/testing-the-journey.md#viewing_logs">閱讀全文</a>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>集中式時區管理</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>時區管理現已集中在歷程屬性面板中。已在歷程屬性中新增兩個參數：</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li><strong>「時區」</strong>下拉式清單可讓您選取特定時區。依預設，系統會使用瀏覽器的時區。 </li>
<li><strong>「設定檔時區」</strong>核取方塊可讓您使用進入歷程之人員的 Adobe Experience Platform 設定檔時區（若有）。否則，系統會使用下拉式清單中定義的時區。此功能與使用沒有命名空間之事件的歷程不相容。</li>
</ul>
<p>如需詳細資訊，請參閱<a href="../building-journeys/changing-properties.md#timezone">變更屬性</a>和<a href="../building-journeys/timezone-management.md">時區管理</a>區段。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>歷程設計器增強功能</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>已增強歷程設計器左側的<strong>浮動視窗</strong>：</p>
<ul>
<li><strong>搜尋</strong>列旁的新圖示可讓您隱藏或顯示浮動視窗中無法使用的元素，例如使用與歷程所用不同之命名空間的事件。依預設，系統會隱藏無法使用的項目。</li>
<li>使用<strong>搜尋</strong>欄位時，現在會顯示每個畫布活動類別的結果數量。</li>
<li>改善不同活動類別之間的導覽。</li>
</ul>
<p>在歷程設計器中，您現在可以檢查自己是否存取最新的歷程版本。此資訊會顯示在版本編號旁邊。</p>
<p>在歷程<strong>畫布</strong>中，當兩個活動中斷連結時，現在會顯示警告訊息。</p>
<img src="../assets/rn-canvas.png"/>
<p>如需詳細資訊，請參閱<a href="../building-journeys/using-the-journey-designer.md">詳細文件</a>。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>內容說明</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>不同的 Journey Orchestration 清單畫面（歷程、事件、動作和資料來源）現在都會提供內容說明。這可讓您檢視目前功能的快速說明，並存取相關文章和影片。</p>
<p>若要顯示內容說明，請按一下畫面右上方的 <img src="../assets/icon-context.png"/> 圖示。 </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**其他改善項目**

* 除了美國以外，Journeys Orchestration 現在已於&#x200B;**歐洲、中東及非洲 (EMEA)**&#x200B;推出。應用程式和文件提供法文版和德文版。

* Experience League 現在已整合至產品中。這可簡化對相關內容的存取，並協助您充分運用 Experience Cloud 的功能。可在 Help 索引標籤底部直接存取 Journey Orchestration 文件。此外，按一下「說明 > 意見回饋」即可回報問題，或與 Adobe 分享您的想法。

* 現在，所有清單畫面（歷程、資料來源、動作和事件）都可以使用 **C** 鍵盤快速鍵來建立新項目。[閱讀全文](../about/user-interface.md#section_ksq_zr1_ffb)

* 您現在可以&#x200B;**刪除**&#x200B;已停止的歷程。系統不會再提供與這些已刪除歷程相關聯的報告。

* 瀏覽 **Adobe Experience Platform 欄位**（XDM 格式）時，您現在除了看到欄位名稱外，還會看到顯示名稱。此資訊會從「Experience 資料模型」的結構定義中擷取。當可用時，畫面就會出現替代顯示名稱。這種容易理解的說明在 eVar 欄位中特別有用，可讓您更輕鬆地識別欄位。[閱讀全文](../about/user-interface.md#friendly-names-display)

## 正式發行 - 2019 年 12 月 {#ga-release---december-2019}

歷程協調正式全面推出。

運用儲存在事件或資料來源中的內容資料，建立即時協調使用案例。

Journey Orchestration 能以事件中的情境資料、Adobe Experience Platform 的資訊或來自協力廠商 API 服務的資料，進行即時協調。應用程式會根據消費者的個人檔案和行為，在稱為歷程的多步驟流程中，決定對該消費者來說下一個最佳的動作。這包括最佳時機和動作類型，例如透過 Adobe Campaign Standard 交易訊息功能（需要有 Adobe Campaign Standard）向消費者傳送推播通知或來自協力廠商系統的通知。這些決定是依據規則和 Sensei 分數加以制定。

[進一步瞭解](../action/working-with-adobe-campaign.md) Journey Orchestration。

其他資源:

* [教學課程](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/introduction.html)
* [社群](https://www.adobe.com/go/journeyorchestrationcommunity)
