---
product: adobe campaign
solution: Journey Orchestration
title: 使用者介面
description: 深一步瞭解使用者介面
feature: Journeys
role: 業務從業人員
level: 中級
translation-type: tm+mt
source-git-commit: f73e357d8947997f7f5872efa6a5ef4f51bc63a9
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 92%

---


# 使用者介面{#concept_rcq_lqt_52b}

>[!NOTE]
>
>若要充分利用 [!DNL Journey Orchestration] 的功能，我們建議使用 Chrome 作為網際網路瀏覽器。介面會以 IMS 中定義的語言顯示。如果 [!DNL Journey Orchestration] 不支援您的 IMS 語言，介面則會以英文顯示。
>
>本文件會經常更新以反映產品最近的異動。不過，有些螢幕擷取畫面可能會與產品的介面稍有不同。

## 存取 [!DNL Journey Orchestration]{#accessing_journey_orchestration}

要訪問[!DNL Journey Orchestration]的介面，請按一下右上角的&#x200B;**[!UICONTROL App Selector]**&#x200B;表徵圖，然後按一下&#x200B;**[!UICONTROL Journey Orchestration]**。

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

在歷程清單 (在 **[!UICONTROL Home]**&#x200B;下) 中，除了 **[!UICONTROL Creation filters]** 外，您還可以根據其狀態和版本 (**[!UICONTROL Status and version filters]**) 篩選顯示的歷程。您也可以選擇只顯示使用特定事件、欄位群組或動作（**[!UICONTROL Activity filters]** 和 **[!UICONTROL Data filters]**）的歷程記錄。**[!UICONTROL Publication filters]** 可讓您選取出版日期或使用者。舉例來說，您可以選擇只顯示昨天發佈之即時歷程的最新版本。請參閱[本頁](../building-journeys/using-the-journey-designer.md)。

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

如果在設定結構時提供了 &quot;xdm:alternateDisplayInfo&quot; 之類的描述元，則好記的名稱會取代顯示名稱。它在使用 “eVars” 和一般欄位時特別有用。您可以透過 API 呼叫來設定好記的名稱描述元。如需詳細資訊，請參閱 [Schema Registry 開發人員指南](https://docs.adobe.com/content/help/zh-Hant/experience-platform/xdm/api/getting-started.html)。

![](../assets/xdm-from-descriptors.png)

如果有好記的名稱，欄位便會顯示為`<friendly-name>(<name>)`。如果沒有好記的名稱，則會顯示顯示名稱`<display-name>(<name>)`。如果未定義這些欄位，則只會顯示欄位的技術名稱 `<name>`。

>[!NOTE]
>
>從結合結構選取欄位時並不會擷取好記名稱。

## 使用不同的捷徑{#section_ksq_zr1_ffb}

以下是 [!DNL Journey Orchestration] 介面提供的不同捷徑。

_在歷程、動作、資料來源或事件清單中：_

* 按下 **C 鍵**&#x200B;以建立新的歷程、動作、資料來源或事件。

_在歷程中設定活動時：_

會自動儲存畫布。您可以在畫布的左上方看到儲存狀態。

* 按下 **ESC 鍵**&#x200B;以關閉設定窗格並捨棄所進行的變更，此功能與 **[!UICONTROL Cancel]** 按鈕相同。
* 按下 **Enter** 或按一下窗格外部以關閉設定窗格，系統便會儲存變更。此功能與 **[!UICONTROL Ok]** 按鈕相同。
* 如果您按下 **Delete** 或&#x200B;**退格鍵**，可以再按下 **Enter** 以確認刪除。

_在快顯視窗中：_

* 按下 **ESC 鍵**&#x200B;以將其關閉（等於 **[!UICONTROL Cancel]** 按鈕）。
* 按下 **Enter** 以儲存或確認（等於 **[!UICONTROL Ok]** 或 **[!UICONTROL Save]** 按鈕）。

_在事件、資料來源或動作設定窗格中：_

* 按下 **ESC 鍵**&#x200B;以關閉設定窗格而不儲存。
* 按下 **Enter** 以儲存修改內容並關閉設定窗格。
* 按下 **Tab 鍵**&#x200B;以在不同欄位之間跳轉並進行設定。

_在簡單運算式編輯器中_

* 在左側欄位上連按兩下以新增查詢（等於拖放）。

_瀏覽 XDM 欄位時：_

* 核取 &quot;node&quot; 即會選取該節點的所有欄位。

_在所有文字區域：_

* 使用 **Ctrl/Command + A** 按鍵組合以選取文字。在有效負載預覽中，系統會選取有效負載。

_在含有搜尋列的畫面中：_

* 使用 **Ctrl/Command + F** 鍵組合以選取搜尋列。

_在歷程的畫布中：_

* 使用 **Ctrl/Command + A** 鍵組合以選取所有動作。
* 選取一或多個活動時，按下 **Delete** 或&#x200B;**空格鍵**&#x200B;以刪除，在確認快顯視窗中按下 **Enter** 以確認。
* 在左側浮動視窗中，在活動上按兩下，以在第一個可用位置（從上到下）新增活動。

_旅程：_

* 按&#x200B;**T**&#x200B;啟用／停用測試模式。
* 在測試模式中的事件型歷程中，按&#x200B;**E**&#x200B;觸發事件。
* 在以區段為基礎的歷程中，當在測試模式中選取「每時&#x200B;**單一描述檔」選項時，按** P **以觸發事件。**
* 在測試模式下，按&#x200B;**L**&#x200B;以顯示日誌。

