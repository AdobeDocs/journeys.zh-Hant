---
product: adobe campaign
solution: Journey Orchestration
title: 使用歷程設計器
description: 進一步瞭解如何使用歷程設計人員
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '1354'
ht-degree: 5%

---


# 使用歷程設計器 {#concept_m1g_5qt_52b}

歷程首頁功能表可讓您檢視 **歷程清單**。 建立新的歷程，或按一下現有的歷程，以開啟歷程設 **計人員的介面**。 設計人員由下列區域組成：浮動視窗、畫布和活動設定窗格。

## 旅程清單 {#journey_list}

The **journey list** allows you to view all your journeys at once, see their status and perform basic actions. 您可以複製、停止或刪除您的歷程。視歷程而定，某些動作可能無法使用。例如，您無法刪除或重新開始已關閉的歷程。您可以從中建立新版本、複製或停止。 也可以使用搜尋列來搜尋歷程。

按一下清單左上方的篩選圖示，即可存取 **[!UICONTROL Filters]**。「篩選」功能表可讓您根據不同的條件（狀態、您建立的、在過去30天內修改的、僅限最新版本等）來篩選顯示的歷程。 您也可以選擇僅顯示使用特定事件、欄位群組或動作的歷程。 清單上顯示的列可以配置。 所有篩選器和欄都會依使用者儲存。

![](../assets/journey74.png)

您所有歷程版本的版本都會出現在清單中，並附上版本號碼。 請參閱[本頁](../building-journeys/journey-versions.md)。

![](../assets/journey37.png)

>[!NOTE]
>
>若要在不同的瀏覽器標籤中開啟旅程的畫布，請按住 **Control** 或 **Command** 鍵，然後按一下旅程。

## 浮動視窗 {#palette}

浮 **動視窗** 位於螢幕的左側。 所有可用活動都分為幾類： **[!UICONTROL Events]**、 **[!UICONTROL Orchestration]** 和 **[!UICONTROL Actions]**。 您可以按一下不同類別的名稱，以展開／收合這些類別。 若要在您的歷程中使用活動，請從浮動視窗拖放至畫布中。 您也可以在下一個步驟中，連按兩下浮動視窗中的活動，將它新增至畫布。 您必須先設定從浮動視窗新增的每個活動，才能發佈歷程。 如果您將活動拖放至畫布中，但未完成其設定，則活動會保留在畫布中，但是紅色警告會指出此活動的設定尚未完成。

>[!NOTE]
>
>請注意，設定旅程時有規則。 不允許的配置將被丟棄。 例如，您無法並行放置動作、將活動連結至上一個步驟以建立回圈、以事件以外的項目開始旅程等。

![](../assets/journey38.png)

The **[!UICONTROL Show disabled items]** icon in the top left corner allows you to hide or display unavailable elements in the palette, for example the events that use a different namespace than the ones used in your journey. 依預設，系統會隱藏無法使用的項目。如果您選擇顯示，則會顯示為灰色。

使用欄位 **[!UICONTROL Search]** 時，會顯示每個畫布活動類別的結果數。

![](../assets/palette-filter.png)

## 畫布 {#canvas}

畫 **布** 是旅程設計人員的中心區域。 您可以在此區域拖放活動並進行設定。 按一下畫布中的活動以進行設定。 這會開啟右側的活動設定窗格。 您可以使用右上角的「+」和「-」按鈕來放大和縮小。 在畫布中，所有活動都允許您在其後新增下一個步驟，但活動 **[!UICONTROL End]** 除外(請參 [閱本頁](../building-journeys/end-activity.md))。

![](../assets/journey39.png)

## 活動配置窗格 {#configuration_pane}

當您 **在浮動視窗中按一下活動** ，就會顯示活動設定窗格。 填寫必填欄位。 按一下圖 **[!UICONTROL Delete]** 示以刪除活動。 按一下 **[!UICONTROL Cancel]** 以取消修改或 **[!UICONTROL Ok]** 確認。 要刪除活動，還可以選擇一個活動（或多個活動），然後按背空格鍵。 按轉義鍵將關閉活動配置窗格。

在畫布中，您的動作和事件活動會以圖示來表示，其下會顯示事件或動作的名稱。 在活動配置窗格中，可以使用 **[!UICONTROL Label]** 欄位為活動名稱添加尾碼。 這些標籤將協助您將事件和動作的使用情境化，尤其是當您在歷程中多次使用相同的事件或動作時。 您也可以看到您在報表中新增的標 [!DNL Journey Orchestration] 簽。 您也可以為條件活動定義標籤。

![](../assets/journey59bis.png)

## 頂端列動作 {#top_actions}

根據旅程的狀態，您可以使用右上角的按鈕在旅程上執行不同的動作： **[!UICONTROL Publish]**, **[!UICONTROL Duplicate]**, **[!UICONTROL Delete]**, **[!UICONTROL Journey properties]**, **[!UICONTROL Test]**&#x200B;未選取任何活動時，這些按鈕就會出現。 有些按鈕會以情境顯示。 測試模式記錄按鈕會在測試模式啟動時顯示(請參 [閱本頁](../building-journeys/testing-the-journey.md))。 當歷程即時、停止或關閉時，會顯示報告按鈕。

![](../assets/journey41.png)

## 在畫布中使用路徑 {#paths}

若發生錯&#x200B;**[!UICONTROL Condition]**&#x200B;誤或逾 **[!UICONTROL Action]** 時，數個活動（活動）可讓您定義備援動作。 在活動配置窗格中，選中該框： **[!UICONTROL Add an alternative path in case of a timeout or an error]**. 活動後會新增另一個路徑。 逾時持續時間在歷程的屬性中定義(由管理 [員使用者](../building-journeys/changing-properties.md) 參閱此頁面)。 例如，如果電子郵件的傳送時間太長或發生錯誤，您可以決定傳送SMS。

![](../assets/journey42.png)

各種活動（事件、動作、等待）可讓您在其後新增數個路徑。 若要這麼做，請將游標置於活動上，然後按一下&quot;+&quot;符號。 只能同時設定事件和等待活動。 如果同時設定多個事件，則選擇的路徑將是第一個發生的事件。

監聽事件時，建議您不要無限期等待該事件。 這並非強制性的，只是最佳做法。 如果您只想在特定時間內監聽一或多個事件，則會並行放置一或多個事件和等待活動。 請參閱[本區段](../building-journeys/event-activities.md#section_vxv_h25_pgb)。

要刪除路徑，請將游標置於路徑上，然後按一下該 **[!UICONTROL Delete arrow]** 表徵圖。

![](../assets/journey42ter.png)

在畫布中，當兩個活動中斷連線時，會顯示警告。 將游標置於警告圖示上，以顯示錯誤訊息。 若要修正問題，只要移動已中斷連線的活動，並將它連線至先前的活動即可。

![](../assets/canvas-disconnected.png)

## 複製和貼上活動 {#copy-paste}

您可以複製某個旅程的一或多個活動，並貼在相同或不同的旅程中。 如果您想要重複使用先前歷程中已設定的許多活動，這可讓您節省時間。

**重要附註**

* 您可以複製／貼到不同的標籤和瀏覽器。 您只能複製／貼上同一例項中的活動。
* 如果目的地歷程中有使用不同名稱空間的事件，則無法複製／貼上事件。
* 貼上的活動可能會參照目標歷程中不存在的資料，例如，如果您複製／貼到不同的沙盒。 請務必檢查錯誤並進行必要的調整。
* 請注意，您無法復原動作。 若要刪除貼上的活動，您必須選取並刪除這些活動。 因此，請務必在複製活動之前僅選擇所需的活動。
* 您可以複製任何歷程中的活動，即使是只讀的活動。
* 您可以選取任何活動，甚至是未連結的活動。 貼上後，連結的活動會保持連結。

以下是複製／貼上活動的步驟：

1. 開啟旅程。
1. 按一下時移動滑鼠，以選取您要複製的活動。 按 **Ctrl/Command鍵時，也可以按一下每個活** 動。 如果要 **選取所有活動，請使用Ctrl/Command + A** 。
   ![](../assets/copy-paste1.png)
1. 按 **Ctrl/Command + C**。
如果只想複製一個活動，可按一下該活動，然後使用活動配置窗格左上角的 **Copy** （複製）表徵圖。
   ![](../assets/copy-paste2.png)
1. 在任何歷程中，按 **Ctrl/Command + V** ，貼上活動，而不將活動連結至現有節點。 貼上的活動會以相同順序放置。 貼上後，活動會保持選取狀態，讓您輕鬆移動。 您也可以將游標置於空的放置器上，然後按 **Ctrl/Command + V**。 貼上的活動將會連結至節點。
   ![](../assets/copy-paste3.png)

