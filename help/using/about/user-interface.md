---
product: adobe campaign
title: 使用者介面
description: 深一步瞭解使用者介面
feature: Journeys
role: User
level: Intermediate
exl-id: 0d0e74c7-6cb0-4068-a69a-3c01f8b3552d
source-git-commit: a5ec1c4c5608113bb17dfbdea0587f6bb342099a
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 93%

---

# 使用者介面{#concept_rcq_lqt_52b}

>[!NOTE]
>
>若要充分利用 [!DNL Journey Orchestration] 的功能，我們建議使用 Chrome 作為網際網路瀏覽器。介面會以 IMS 中定義的語言顯示。如果 [!DNL Journey Orchestration] 不支援您的 IMS 語言，介面則會以英文顯示。
>
>本文件將經常更新，以反應產品近期異動。不過，有些螢幕擷取畫面可能會與產品的介面稍有不同。

## 存取 [!DNL Journey Orchestration]{#accessing_journey_orchestration}

若要存取 [!DNL Journey Orchestration]的介面，按一下 **[!UICONTROL App Selector]** 圖示，然後在右上方，按一下 **[!UICONTROL Journey Orchestration]**.

![](../assets/journey1.png)

您也可以從 Experience Cloud 首頁的 **[!UICONTROL Quick access]** 區段存取 [!DNL Journey Orchestration]

![](../assets/journey1bis.png)

## 探索介面{#section_jsq_zr1_ffb}

>[!CONTEXTUALHELP]
>id="jo_home"
>title="關於歷程清單"
>abstract="歷程清單可讓您一次檢視所有歷程、查看其狀態並執行基本動作。"
>additional-url="https://images-tv.adobe.com/mpcv3/38af62cb-9390-4bc0-a576-d336849adb97_1574809570.1920x1080at3000_h264.mp4" text="觀看示範影片"

頂頂端功能表可讓您導覽[!DNL Journey Orchestration]　的不同功能：**[!UICONTROL Home]**（歷程）、**[!UICONTROL Data Sources]**、**[!UICONTROL Events]**、**[!UICONTROL Actions]**。

![](../assets/journey2.png)

按一下畫面右上角的 ![](../assets/icon-context.png) 圖示以顯示內容說明，它會顯示在不同的 [!DNL Journey Orchestration] 清單畫面中（歷程、事件、動作和資料來源）。這可讓您檢視目前功能的快速說明，並存取相關文章和影片。

![](../assets/journey2bis.png)

## 搜尋和篩選{#section_lgm_hpz_pgb}

在&#x200B;**[!UICONTROL Home]**、**[!UICONTROL Data Sources]**、**[!UICONTROL Events]** 和 **[!UICONTROL Actions]** 清單中，搜尋列可讓您搜尋項目。

按一下清單左上方的篩選圖示，即可存取 **[!UICONTROL Filters]**。篩選選單可讓您根據不同的條件篩選顯示的元素。您可以選擇僅顯示某一類型或狀態的元素、您建立的元素，或者在過去 30 天內修改的元素。

在 **[!UICONTROL Data Sources]**、**[!UICONTROL Events]** 和 **[!UICONTROL Actions]** 清單中，使用 **[!UICONTROL Creation filters]** 建立篩選器以篩選建立日期和使用者。舉例來說，您可以選擇只顯示您在過去 30 天內建立的事件。

在歷程清單中（在下） **[!UICONTROL Home]**)，以及 **[!UICONTROL Creation filters]**，您也可以根據顯示的歷程狀態、型別和版本(**[!UICONTROL Status and version filters]**)。 型別可以是： **[!UICONTROL Unitary event]** 或 **[!UICONTROL Segment qualification]**. 您也可以選擇只顯示使用特定事件、欄位群組或動作（**[!UICONTROL Activity filters]** 和 **[!UICONTROL Data filters]**）的歷程記錄。**[!UICONTROL Publication filters]** 可讓您選取出版日期或使用者。舉例來說，您可以選擇只顯示昨天發佈之即時歷程的最新版本。請參閱[此頁面](../building-journeys/using-the-journey-designer.md)。

>[!NOTE]
>
>請注意，顯示的欄可使用清單右上角的設定按鈕進行個人化。系統會為每位使用者儲存個人化設定。

**[!UICONTROL Last update]** 和 **[!UICONTROL Last update by]** 欄可讓您顯示上次出現歷程更新的時間，以及操作歷程的使用者。

![](../assets/journey74.png)

在事件、資料來源和動作設定窗格中，**[!UICONTROL Used in]** 欄位會顯示使用該特定事件、欄位群組或動作的歷程次數。您可以按一下 **[!UICONTROL View journeys]** 按鈕以顯示對應歷程的清單。

![](../assets/journey3bis.png)

在不同的清單中，您可以對每個元素執行基本動作。例如，您可以複製或刪除項目。

![](../assets/journey4.png)

## 瀏覽 Adobe Experience Platform 欄位 {#friendly-names-display}

定義[事件有效負載](../event/defining-the-payload-fields.md)、[欄位群組有效負載](../datasource/field-groups.md)，以及在[運算式編輯器](../expression/expressionadvanced.md)中選取欄位時，除了欄位名稱外，還會顯示顯示名稱。此資訊會從「Experience 資料模型」的結構定義中擷取。

如果在設定結構時提供了 &quot;xdm:alternateDisplayInfo&quot; 之類的描述元，則好記的名稱會取代顯示名稱。它在使用 “eVars” 和一般欄位時特別有用。您可以透過 API 呼叫來設定好記的名稱描述元。如需詳細資訊，請參閱 [Schema Registry 開發人員指南](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=zh-Hant)。

![](../assets/xdm-from-descriptors.png)

如果有好記的名稱，欄位便會顯示為`<friendly-name>(<name>)`。如果沒有好記的名稱，則會顯示顯示名稱`<display-name>(<name>)`。如果未定義這些欄位，則只會顯示欄位的技術名稱 `<name>`。

>[!NOTE]
>
>從結合結構選取欄位時並不會擷取好記名稱。

## 協助工具{#accessibility}

Adobe Journey Optimizer中的協助工具功能由Adobe Experience Platform提供：

* 鍵盤協助工具
* 顏色對比
* 驗證必填欄位

透過 Adobe Experience Platform 文件[了解更多](https://experienceleague.adobe.com/docs/experience-platform/accessibility/features.html?lang=zh-Hant){target="_blank"}。

您可以在Adobe Journey Optimizer中使用這些常見的鍵盤快速鍵：

| 動作 | 快速鍵 |
| --- | --- |
| 在使用者介面元素、區段和功能表群組之間移動 | Tab 鍵 |
| 在使用者介面元素、區段和功能表群組之間向後移動 | Shift + Tab 鍵 |
| 在區段內移動並將焦點設定為個別元素 | 箭頭 |
| 選取或清除焦點中的元素 | 輸入或空格鍵 |
| 取消選取、折疊面板或關閉對話方塊 | Esc 鍵 |

透過 Adobe Experience Platform 文件[了解更多](https://experienceleague.adobe.com/docs/experience-platform/accessibility/custom.html?lang=zh-Hant){target="_blank"}。

您可以在 Journey Optimizer 的特定部分使用下列快速鍵：

<table>
  <thead>
    <tr>
      <th>介面元素</th>
      <th>動作</th>
      <th>快速鍵</th>
    </tr>
  </thead>
  <tr>
    <td>歷程、動作、資料來源或事件清單</td>
    <td>建立歷程、動作、資料來源或事件</td>
    <td>C</td>
  </tr>
  <tr>
    <td rowspan="3">草稿狀態的歷程畫布</td>
    <td>從左側色盤的第一個可用位置 (從上到下) 新增活動</td>
    <td>在活動上按兩下</td>
  </tr>
  <tr>
    <td>選取所有活動</td>
    <td>Ctrl + A (Windows)<br/> Command + A (Mac)</td>
  </tr>
  <tr>
    <td>刪除選取的活動</td>
    <td>刪除或退格，然後輸入以確認刪除</td>
  </tr>
  <tr>
  <td rowspan="3">

這些元素的設定窗格：

<ul>
  <li>歷程中的活動</li>
  <li>事件</li>
  <li>資料來源</li>
  <li>動作</li>
</ul>

</td>
    <td>移至下一個要設定的欄位</td>
    <td>Tab 鍵</td>
  </tr>
  <tr>
    <td>儲存變更並關閉設定窗格</td>
    <td>Enter 鍵</td>
  </tr>
  <tr>
    <td>放棄變更並關閉設定窗格</td>
    <td>Esc 鍵</td>
  </tr>
  <tr>
    <td rowspan="4">測試模式中的歷程</td>
    <td>啟用或停用測試模式</td>
    <td>T</td>
  </tr>
  <tr>
    <td>觸發事件歷程中的事件</td>
    <td>E</td>
  </tr>
  <tr>
    <td>

在區段型歷程中觸發事件，其 **[!UICONTROL Single profile at a time]** 選項為開啟

</td>
    <td>P</td>
  </tr>
  <tr>
    <td>顯示測試記錄</td>
    <td>L</td>
  </tr>
<!-- //Ajouter ce raccourci quand il marchera (actuellement, le raccourci Ctrl/Cmd+F du navigateur a priorité sur celui de AJO).//
  <tr>
    <td>Page with a search bar</td>
    <td>Select the search bar</td>
    <td>Ctrl/Command + F</td>
  </tr>
-->
  <tr>
    <td>文字欄位</td>
    <td>選取所選欄位中的所有文字</td>
    <td>Ctrl + A (Windows)<br/> Command + A (Mac)</td>
  </tr>
  <tr>
    <td rowspan="2">快顯視窗</td>
    <td>儲存變更或確認動作</td>
    <td>Enter 鍵</td>
  </tr>
  <tr>
    <td>關閉視窗</td>
    <td>Esc 鍵</td>
  </tr>
  <tr>
    <td>簡易運算式編輯器</td>
    <td>選取並新增欄位</td>
    <td>在欄位上按兩下</td>
  </tr>
  <tr>
    <td>瀏覽 XDM 欄位</td>
    <td>選取節點的所有欄位</td>
    <td>選擇上層節點</td>
  </tr>
  <tr>
    <td>內容預覽</td>
    <td>選取內容</td>
    <td>Ctrl + A (Windows)<br/> Command + A (Mac)</td>
  </tr>
</table>
