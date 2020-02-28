---
title: 發行說明 年
description: 瞭解版本注意事項
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 73f1a503ea2c8b3494460c666a05078ed914e58b

---


# 發行說明 {#release-notes}

本頁列出Journey Orchestration的所有新功能和改進。
您也可以參閱「檔案 [更新」](../release-notes/documentation-updates.md)。

## 第1季發行- 2020年3月 {#q1-release---march-2020}

**新增功能？**

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
<li>當旅程使用數個事件時，您現在可以在測試模式的「事件設定」畫面中，從下拉式清單中個別觸發每個事件 <strong></strong> 。 <a href="../building-journeys/testing-the-journey.md#firing_events">閱讀更多資訊</a></p></li>
<li><p>當在歷程中使 <strong>用一或多個</strong> 「等待」活動時，您現在可以定義每個活動在測試模式中的持續時間。 預設時間為10秒。 您可以使用左下角的 <strong>「在測試中等待時間</strong> 」參數來變更此項。 <a href="../building-journeys/testing-the-journey.md">閱讀更多資訊</a></p><img src="../assets/rn-test.png"/>
</li>
<li>在測 <strong>試記錄</strong>，如果呼叫協力廠商系統（資料來源或動作）時發生錯誤，現在會顯示錯誤碼和錯誤回應。 <a href="../building-journeys/testing-the-journey.md#viewing_logs">閱讀更多資訊</a>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>集中的時區管理</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>時區管理現在集中在歷程屬性面板中。 在歷程屬性中新增了兩個參數：</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li>「 <strong>時區</strong> 」下拉式清單可讓您選取特定時區。 依預設，會使用瀏覽器的時區。</li>
<li>「描 <strong>述檔時區</strong> 」核取方塊可讓您使用進入歷程之人員的「體驗平台描述檔」時區（如果有的話）。 否則，會使用下拉式清單中定義的時區。 此功能與使用沒有命名空間之事件的歷程不相容。</li>
</ul>
<p>如需詳細資訊，請參閱「變更 <a href="../building-journeys/changing-properties.md#timezone">屬性</a> 」和「 <a href="../building-journeys/timezone-management.md">時區管理</a> 」區段。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>歷程設計人員增強功能</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>旅程 <strong>設計人員</strong>（在旅程設計人員左側）的旅程浮動視窗已增強：</p>
<ul>
<li>在**Search**列旁有新圖示，可讓您隱藏或顯示浮動視窗中不可用的元素，例如使用不同於歷程中所用名稱空間的事件。 依預設，無法使用的項目會隱藏。</li>
<li>使用「搜 <strong>尋</strong> 」欄位時，現在會顯示每個畫布活動類別的結果數。</li>
<li>已改善不同活動類別之間的導覽。</li>
</ul>
<p>在歷程設計人員中，您現在可以檢查您是否正在存取歷程的最新版本。 此資訊會顯示在版本號碼旁邊。</p>
<p>在歷程畫 <strong>布中</strong>，當兩個活動中斷連線時，現在會顯示警告訊息。</p>
<img src="../assets/rn-canvas.png"/>
<p>如需詳細資訊，請參閱詳 <a href="../building-journeys/using-the-journey-designer.md">細檔案</a>。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>內容相關說明</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>現在，不同的「歷程協調」清單畫面（歷程、事件、動作和資料來源）都提供內容相關的說明。 這可讓您檢視目前功能的快速說明，並存取相關文章和影片。</p>
<p>若要顯示內容相關說明，請 <img src="../assets/icon-context.png"/> 按一下畫面右上角的圖示。 </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**其他改進**

* 除了美國以外，Journeys Orchestration現在在 **EMEA提供**。 應用程式和檔案提供法文和德文版。

* Experience League現在已整合至產品中。 這可簡化對相關內容的存取，並協助您充份運用Experience Cloud。 直接存取Journey Orchestration檔案，位於「說明」標籤底部。 此外，按一下「說明>意見回應」以報告問題，或與Adobe分享您的想法。

* 現在 **所有清單畫面都可使用C** 鍵盤快速鍵，讓您建立新項目：歷程、資料來源、動作和事件。 [閱讀更多資訊](../about/user-interface.md#section_ksq_zr1_ffb)

* 您現在可以刪 **除已停** 止的歷程。 與這些已刪除的歷程相關聯的報告將不可用。

* 瀏覽「資 **料平台」欄位** （XDM格式）時，您現在除了看到欄位名稱外，還會看到顯示名稱。 此資訊會從「體驗資料模型」的架構定義中擷取。 當可用時，將顯示替代顯示名稱。 此使用者友好的說明（在eVar欄位中特別有用）可讓您更輕鬆地識別欄位。 [閱讀更多資訊](../about/user-interface.md#friendly-names-display)

## 正式發行- 2019年12月 {#ga-release---december-2019}

歷程協調現在正式推出。

運用儲存在事件或資料來源中的情境資料，建立即時協調使用案例。

Journey Orchestration可讓您即時協調，並運用來自活動的情境式資料、來自Adobe Experience Platform的資訊或來自協力廠商API服務的資料。 應用程式會根據消費者的描述檔和行為，在稱為歷程的多步驟流程中，決定下一個消費者專屬的最佳動作。 這包括最佳時機和動作類型，例如透過Adobe Campaign standard交易訊息功能（需要Adobe Campaign Standard）向消費者傳送推播通知或通知協力廠商系統。 這些決定是根據規則和Sensei得分做出的。

[進一步瞭解](../action/working-with-adobe-campaign.md) 「歷程協調」。

其他資源：

* [教學課程](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [社群](https://www.adobe.com/go/journeyorchestrationcommunity)