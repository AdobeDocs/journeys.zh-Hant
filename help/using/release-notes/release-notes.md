---
product: adobe campaign
title: 版本注意事項
description: 瞭解發行說明
feature: Journeys
role: User
level: Beginner
exl-id: b923f7e3-997b-483b-b6ac-eef62fc81a84
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '3274'
ht-degree: 98%

---

# 版本注意事項 {#release-notes}

本頁面列出 Journey Orchestration 的所有新功能和改進項目。
您也可以參閱最新的[文件更新](../release-notes/documentation-updates.md)。

## 2022 年 5 月發行 {#may-2022-release}

### 改進項目

* **表達式編輯器** - [限](../functions/functionlimit.md) 已添加函式，以允許您限制清單的項數。 的 [排序](../functions/functionsort.md) 函式現在允許您對清單對象進行排序。 對listObject的支援也添加到 [斷層](../functions/functiondistinct.md) 和 [distinctWithNull](../functions/functiondistinctwithnull.md) 的子菜單。

## 2022 年 3 月發行 {#feb-2022-release}

### 改進項目

* 為避免統一設定檔綱要存在不必要的欄位，預設情況下不再為設定檔啟用「歷程步驟事件」綱要。 如有需要，可以啟用。 [了解更多](../building-journeys/sharing-overview.md)
* 跟匯出工作有關的新步驟活動現在由 Journey Optimizer 傳送到 Adobe Experience Platform。 已在文件中新增查詢範例。 [了解更多](../building-journeys/query-examples.md)

## 2022 年 2 月發佈內容 {#february-2022-release}

### 改進項目

* 為了最佳化效能和避免過時資源的使用，所有處於測試模式且一週內未觸發的歷程現在將切換回「草稿」狀態。 [閱讀全文](../building-journeys/testing-the-journey.md#important_notes)

## 2022 年 1 月發行版本 {#january-2022-release}

### 改進項目

* Journey Orchestration 步驟事件現在可以連結到 [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hant) 中的其他資料集。  內建「歷程步驟事件」方案中的 **profileID** 欄位現在定義為身分欄位。 [了解更多](../building-journeys/sharing-overview.md#integration-cja)
* Adobe Campaign Standard 操作的上限規則已更改為 4000 次呼叫 / 5 分鐘。[閱讀全文](../action/working-with-adobe-campaign.md)

## 2021 年 10 月發行版本 {#october-2021-release}

### 改進項目

* **運算式編輯器**  - 身為超級使用者，您現在可以使用函式來處理地圖。 [了解更多](../expression/field-references.md)
* **協助工具**  - 已實施協助工具增強功能。Journey Orchestration 的協助工具現在可完全相容。
* **集合**  - 現在支援包含子物件的物件陣列。 [閱讀全文](../usecase/collections.md)
* **監控**  - 已增強即時歷程和測試模式的步驟事件。 [新欄位](../building-journeys/sharing-field-list.md#serviceevents) 已新增與設定檔匯出作業有關的內容。 為了獲得更好的使用者體驗，步驟事件欄位現已移至「歷程步驟事件」綱要的其他類別以便進行 Journey Orchestration。所有先前的步驟事件欄位仍可在 [stepEvents](../building-journeys/sharing-legacy-fields.md) 類別中使用。

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
* 在為規則型事件定義事件 ID 條件時，「contains」運算元現在可用於字串類型欄位。 [進一步了解](../event/about-creating.md)

## 2021 年 8 月發行版本 {#august-2021-release}

### 改進項目

**歷程**

* **動態標頭** - 您現在可以在 HTTP 標頭參數中傳遞動態資料。 接收歷程動作 HTTP 呼叫的整合系統可使用這些參數 (例如時間戳記或追蹤 ID)。 [閱讀全文](../action/url-configuration.md)
* **Dynamic URL 路徑** - 您現在可以為自訂動作設定動態 URL 路徑。 [閱讀全文](../action/url-configuration.md)

## 2021 年 7 月發行版本 {#july-2021-release}

<table>
<thead>
<tr>
<th><strong>利用綱要關係</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform 可讓您定義綱要之間的關係，以便將一個資料集用作另一個資料集的查詢表。 Journey Orchestration 現在可以利用來自連結綱要的資料。</p>
<p>可在單一事件設定、歷程狀況和自訂動作個人化提供這些欄位。
<p>如需詳細資訊，請參閱<a href="../event/experience-event-schema.md#leverage_schema_relationships">詳細文件</a>。</p>
</td>
</tr>
</tbody>
</table>

### 改進項目

* **快取期間** 欄位已從資料來源設定窗格中移除。 [閱讀全文](../datasource/about-data-sources.md)

## 2021 年 6 月發行版本 {#june-2021-release}

<table>
<thead>
<tr>
<th><strong> Adobe Campaign Classic 整合</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>透過 Adobe Campaign Classic 的整合功能現在整合為 GA。 這允許您使用 Adobe Campaign v7 或 v8 傳送訊息的能力來傳送電子郵件、傳送通知及 SMS。</p>
<p>Journey Orchestration 與 Campaign 執行個體之間的連線在佈建時由 Adobe 設定。</p>
<p>如需詳細資訊，請參閱<a href="../action/acc-action.md">詳細文件</a>。</p>
</td>
</tr>
</tbody>
</table>

### 改進項目

* 對於外部資料來源，現在會自動定義每秒 15 次呼叫的上限規則。 [閱讀全文](../about/external-systems.md#capping)
* 簡易和進階運算式編輯器現在支援 XDM 日期格式。
* 在歷程清單畫面，新增了篩選器。 您現在可以透過歷程類別來篩選：**[!UICONTROL Unitary event]** 或 **[!UICONTROL Segment qualification]**。 [閱讀全文](../about/user-interface.md#section_lgm_hpz_pgb)
* 對於即時歷程，歷程屬性畫面現在會顯示發佈日期和發佈歷程的使用者名稱。 當您複製歷程的詳細技術資訊時，也可以獲得此資訊。 [閱讀全文](../building-journeys/changing-properties.md#section_lgm_hpz_pgb)

## 2021 年 4 月發行版本 {#april-2021-release}

### 改進項目

* 在測試模式的&#x200B;**事件設定**&#x200B;畫面中，對於預期分項清單的欄位，現在會顯示下拉清單。 只要選擇一個可用的值。如果定義了錯誤值，這可避免在觸發事件時發生錯誤。 [閱讀全文](../building-journeys/testing-the-journey.md#firing_events)

## 2021 年 3 月發行版本 {#march-2021-release}

### 改進項目

* 已在歷程加入新狀態。 歷程結束或手動關閉時，其狀態將在關閉 30 天後從&#x200B;**已關閉**&#x200B;轉換為&#x200B;**已完成**。 這樣您就可以更輕鬆辨識未啟用的歷程，同時確保仍在場的所有個人有時間完成歷程。 [閱讀全文](../building-journeys/journey.md#ending_a_journey)
* 在歷程草稿的活動右窗格，唯讀欄位預設為隱藏。 這種介面簡化可讓您設定活動更輕鬆。 如要顯示，請按一下&#x200B;**顯示唯讀欄位**&#x200B;圖示，可在活動設定窗格的左上角找到。 [閱讀全文](../building-journeys/using-the-journey-designer.md#configuration_pane)
* 在測試模式的&#x200B;**事件設定**&#x200B;畫面， 用於定義測試個人檔案 ID 的&#x200B;**鍵值**&#x200B;欄位已更名為&#x200B;**個人檔案識別碼**&#x200B;以便獲得更好的使用者體驗。 [閱讀全文](../building-journeys/testing-the-journey.md)。
* 對於反應事件，現在只能把逾時期間設定在 40 秒到 30 天之間。 測試歷程的反應事件時，測試模式 **[!UICONTROL Wait time]** 預設值及最小值現在是 40 秒。 [閱讀全文](../building-journeys/reaction-events.md)。

## 2021 年 2 月發行版本 {#february-2021-release}

<table>
<thead>
<tr>
<th><strong>更新個人檔案活動</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>這個新的動作活動可讓您利用來自事件、資料來源或使用特定值的資料來更新現有 Adobe Experience Platform 個人資料。</p>
<p>如需詳細資訊，請參閱<a href="../building-journeys/update-profiles.md">詳細文件</a>。</p>
</td>
</tr>
</tbody>
</table>

### 其他改善項目

* 現在，當設定事件時，預設只會預選 XDM 驗證的必要欄位。 無法取消選擇這些欄位。
* 已在歷程調色盤加入新篩選器。 除了現成可用的項目外，還可讓您僅顯示最近使用的五個事件及動作。 這特定於每位使用者。 預設情況下，所有項目都會顯示。 [閱讀全文](../building-journeys/using-the-journey-designer.md#palette)
* 開始新歷程時，不能在第一步驟放入畫布的元素現在已隱藏。 這關係到所有動作、狀況活動、等待和反應。
* 在進階運算式編輯器的左側部分，函式現在重新組合在清單末尾的&#x200B;**函式**&#x200B;區段。

## 2021 年 1 月發行版本 {#january-2021-release}

在事件設定中選擇綱要時，只會選擇事件的必要欄位，以使 Journey Orchestration 正確接收事件。 [閱讀全文](../event/defining-the-payload-fields.md)

現可在簡易運算式編輯器使用歷程屬性。 [閱讀全文](../expression/journey-properties.md)

增加兩個新的歷程屬性 (sandboxName 和 organizationId)。 [閱讀全文](../expression/journey-properties.md)

為了跟 Adobe Campaign Standard SLA 保持一致，一旦設定了 Adobe Campaign Standard 整合功能，Adobe Campaign Standard 會自動定義每秒 13 次呼叫的上限規則。 [閱讀全文](../action/working-with-adobe-campaign.md)

逾時路徑現在更清楚指定事件逾時期間。 [閱讀全文](../building-journeys/event-activities.md#listening-to-events-during-a-specific-time)

[getListItem](../functions/functiongetlistitem.md) 與 [split](../functions/functionsplit.md) 函式已在進階運算式編輯器中加入可用函式清單。 這將為字串計算使用案例提供更多可能性。

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
<p>新動作活動可讓您把個人從一個歷程推送到另一個歷程。 <strong>「跳轉」</strong>活動允許您 :
</p>
<ul>
<li>將複雜歷程分割為數個歷程，以簡化極為複雜的設計 </li>
<li>根據常見且可重複使用的歷程模式來建立歷程</li>
</ul>
<p>如需更多詳細資訊，請參閱<a href="../building-journeys/jump.md">詳細文件</a>及<a href="https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html?lang=zh-Hant">教學影片</a>。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>在運算式編輯器使用歷程屬性</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>我們進階運算式編輯器的欄位和函式清單加入了新選項。 這是系統從即時歷程擷取的資訊，例如歷程 ID 或遇到的特定錯誤。 當您建立歷程時，這可為您帶來更多可能性。 例如，如果在狀況或動作中發生錯誤，您能夠提醒協力廠商系統。
</p>
<p>如需詳細資訊，請參閱<a href="../expression/journey-properties.md">相關的文件</a>，以瞭解詳情。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>規則型事件(beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>現在有個新方法讓設定事件更輕鬆，而無需使用 eventID : 根據狀況由規則評估是否需要觸發事件。 您仍然可以使用現有方法，現在稱為「由系統產生」。 在 Alpha 方案對有限客戶測試這項功能，現在向所有客戶提供 Beta 版。
</p>
</td>
</tr>
</tbody>
</table>

### 其他改善項目

在建立歷程的新版本時增加了限制。 這些限制避免歷程變化過於劇烈，讓版本之間保持部分一致性。 [閱讀全文](../about/limitations.md#journey-versions-limitations)

**區段資格**&#x200B;活動不能再用於包含 Campaign Standard 訊息活動的歷程。 這個限制保護了 Adobe Campaign Standard 執行個體的完整性。 事實上，使用區段資格可能會導致每天傳送訊息的高峰，讓 Campaign Standard 異動訊息過載。 [閱讀全文](../about/limitations.md#segment-qualification)

## 2020 年 10 月發行版本 {#october-release}

<table>
<thead>
<tr>
<th><strong>事件逾時</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>現在，您可以為事件設定逾時，以便讓歷程只在特定時間監聽事件。 您不再需要在事件路徑上同時加入等待活動來達成這個目的。
</p>
<p>如需詳細資訊，請參閱<a href="../building-journeys/event-activities.md#listening-to-events-during-a-specific-time">詳細文件</a>。</p>
</td>
</tr>
</tbody>
</table>

### 其他改善項目

* 當您發佈歷程的新版本時，會自動關閉舊版本並切換到「已關閉」狀態。 [閱讀全文](../building-journeys/journey-versions.md)

## 2020 年 9 月發行版本 {#september-release}

### GA 更新{#september-ga-update}

<table>
<thead>
<tr>
<th><strong>狀況活動改進項目</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>把狀況加入歷程後，您現在可以定義標籤。 如果歷程包含數個狀況，這可讓您更容易識別。
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
<th><strong>在讀取區段活動方面的改進</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>已針對<strong>讀取區段</strong>活動進行下列改進 :
</p>
<ul>
<li><p>現在，區段類歷程會顯示在畫布上方，提醒您歷程的排程類型。 您可以按一下此提醒存取排程設定功能表。</p>
</li>
<li><p>已改進測試模式記錄的詳細程度，顯示區段匯出的進度狀態。</p>
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

## Alpha 發行版本 - 2020 年 7 月 {#alpha-release---july-2020}

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


## 第 2 季度發布內容 - 2020 年 6 月 {#q2-release---june-2020}

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
<li><p>在簡單運算式編輯器中，Adobe Experience Platform 區段現在會直接列在導覽樹狀結構中，以方便設定「does this person belong to segment A?」等條件。<a href="../segment/using-a-segment.md">閱讀全文</a></p>
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

## 第 1 季度發布內容 - 2020 年 3 月 {#q1-release---march-2020}

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

* [教學課程](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/introduction.html?lang=zh-Hant)
* [社群](https://www.adobe.com/go/journeyorchestrationcommunity)
