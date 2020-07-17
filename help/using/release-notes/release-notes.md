---
title: 發行說明
description: 瞭解發行說明
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '1107'
ht-degree: 66%

---


# 發行說明{#release-notes}

本頁面列出 Journey Orchestration 的所有新功能和改善項目。
您也可以參閱[文件更新](../release-notes/documentation-updates.md)。

## 第2季度發行- 2020年6月 {#q2-release---june-2020}

<table>
<thead>
<tr>
<th><strong>Adobe Experience Platform整合增強功能</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>已進行下列Adobe Experience Platform整合增強：</p>
<ul>
<li><p>新活動可讓您監聽Adobe Experience Platform區段的入口／出口，讓人們在旅程中進入或前進。 <a href="../building-journeys/segment-qualification-events.md">詳細內容</a></p>
<img src="../assets/rn-segment7.png"/>
</li>
<li><p>有了新的「區段」索引標籤，您現在不需離開「歷程協調」介面，就可以建立和編輯Adobe Experience Platform <strong>區段</strong> 。<a href="../segment/about-segments.md">詳細內容</a></p>
<img src="../assets/rn-segment1.png"/>
</li>
<li><p>在簡單運算式編輯器中，Adobe Experience Platform區段現在會直接列在導覽樹狀結構中，以方便設定條件，例如「此人是否屬於區段A?」。<a href="../segment/using-a-segment.md">詳細內容</a></p>
<img src="../assets/rn-segment4.png"/>
</li>
<li><p>Journey Orchestration現在會自動傳遞至Adobe Experience Platform，讓您在歷程中執行的步驟。 這包括可能遇到的錯誤。 此資訊可用於執行特定旅程或所有旅程之旅程步驟事件的查詢，以建立報告和疑難排解。 <a href="../building-journeys/sharing-overview.md">詳細內容</a></p>
<img src="../assets/rn-journeystepevent.png"/>
</li>
</li>
<li><p>現在，「歷程協調」可以與製作和非製作的Adobe Experience Platform沙盒連接。 請注意，沙盒是測試版功能。 <a href="../about/access-management.md#sandboxes">詳細內容</a></p>
</li>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>歷程設計與測試模式增強功能</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>歷程設計人員和測試模式已進行下列增強：</p>
<ul>
<li><p>您現在可以將貼上活動從一個歷程複製到另一個歷程，選擇1或N個歷程活動。 <a href="../building-journeys/using-the-journey-designer.md#copy-paste">詳細內容</a></p>
<img src="../assets/rn-copy-paste1.png"/>
</li>
<li><p>在觸發事件以讓測試描述檔進入歷程後，您現在可以透過彩色的視覺流程，看到歷程中的進度。 在旅程中發生錯誤時，也會顯示錯誤的詳細資訊。 <a href="../building-journeys/testing-the-journey.md#firing_events">詳細內容</a></p>
<img src="../assets/rn-journeytest6.png"/>
</li>
<li>「完 <strong>成的旅程</strong> 」狀態已更名為「 <strong>關閉（無入口）</strong> 」，以更好地反映此狀態的含義。</li>
</ul>
</td>
</tr>
</tbody>
</table>

**其他改善項目**

為避免傳送過多的API呼叫至協力廠商系統，我們推出新的公用API來設定「限制」規則。 封閉規則允許定義每毫秒對API端點的最大調用數。 [詳細內容](../api/capping.md)

存取控制現在允許使用者存取管理更精細。 有效的可用性： 2020年6月30日。 [詳細內容](../about/access-management.md#create-product-profile)

Journey Orchestration現在已在APAC（澳洲資料中心）提供。 有效的可用性： 2020年6月30日

Journey Orchestration介面提供日文版。

## 第 1 季發行 - 2020 年 3 月{#q1-release---march-2020}

**新增功能?**

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
<li>如果歷程使用數個事件，您現在可以在測試模式的<strong>「事件設定」</strong>畫面中，從下拉式清單中個別觸發每個事件。<a href="../building-journeys/testing-the-journey.md#firing_events">詳細內容</a></p></li>
<li><p>如果歷程中使用一或多個<strong>「等待」</strong>活動，您現在可以定義每個活動在測試模式中的持續時間。預設時間為 10 秒。您可以使用左下角的<strong>「測試等待時間」</strong>參數來變更此項目。<a href="../building-journeys/testing-the-journey.md">詳細內容</a></p><img src="../assets/rn-test.png"/>
</li>
<li>在<strong>測試記錄</strong>中，如果在呼叫協力廠商系統 (資料來源或動作) 時發生錯誤，現在會顯示錯誤代碼和錯誤回應。<a href="../building-journeys/testing-the-journey.md#viewing_logs">詳細內容</a>
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
<li>The <strong>Profile Timezone</strong> checkbox allows you to use the Adobe Experience Platform Profile timezone of the person entering the journey, if available. 否則，系統會使用下拉式清單中定義的時區。此功能與使用沒有命名空間之事件的歷程不相容。</li>
</ul>
<p>如需詳細資訊，請參見<a href="../building-journeys/changing-properties.md#timezone">變更屬性</a>和<a href="../building-journeys/timezone-management.md">時區管理</a>章節。</p>
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
<p>如需詳細資訊，請參見<a href="../building-journeys/using-the-journey-designer.md">詳細文件</a>。</p>
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
<p>不同的 Journey Orchestration 清單畫面 (歷程、事件、動作和資料來源) 現在都會提供內容說明。這可讓您檢視目前功能的快速說明，並存取相關文章和影片。</p>
<p>若要顯示內容說明，請按一下畫面右上角的 <img src="../assets/icon-context.png"/>圖示。 </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**其他改善項目**

* 除了美國以外，Journeys Orchestration 現在已於&#x200B;**歐洲、中東及非洲**&#x200B;推出。應用程式和文件提供法文和德文版。

* Experience League 現在已整合至產品中。這可簡化對相關內容的存取，並協助您充分運用 Experience Cloud 的功能。可在「說明」標籤底部直接存取 Journey Orchestration 文件。此外，按一下「說明 > 意見回饋」即可報告問題，或與 Adobe 分享您的想法。

* 現在，所有清單畫面 (歷程、資料來源、動作和事件) 都可以使用 **C** 鍵盤快速鍵來建立新項目。[詳細內容](../about/user-interface.md#section_ksq_zr1_ffb)

* 您現在可以&#x200B;**刪除**&#x200B;已停止的歷程。系統不會再提供與這些已刪除歷程相關聯的報告。

* When browsing through **Adobe Experience Platform fields** (XDM format), you will now see the display name in addition to the field name. 此資訊會從「Experience 資料模型」的結構定義中擷取。當可用時，畫面就會出現替代顯示名稱。這種容易理解的說明在 eVar 欄位中特別有用，可讓您更輕鬆地識別欄位。[詳細內容](../about/user-interface.md#friendly-names-display)

## 正式發行 - 2019 年 12 月{#ga-release---december-2019}

Journey Orchestration 現在已正式推出。

善用儲存在事件或資料來源中的情境資料，建立即時協調使用案例。

Journey Orchestration 允許以事件中的情境資料、Adobe Experience Platform 的資訊或來自協力廠商 API 服務的資料，進行即時協調。應用程式會根據消費者的個人檔案和行為，在稱為歷程的多步驟流程中，決定對該消費者來說下一個最佳的動作。這包括最佳時機和動作類型，例如透過 Adobe Campaign Standard 交易訊息功能 (需要有 Adobe Campaign Standard) 向消費者傳送推播通知或來自協力廠商系統的通知。這些決定是根據規則和 Sensei 分數所得。

[進一步瞭解](../action/working-with-adobe-campaign.md) Journey Orchestration。

其他資源：

* [教學課程](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [社群](https://www.adobe.com/go/journeyorchestrationcommunity)
