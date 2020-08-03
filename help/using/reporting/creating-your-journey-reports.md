---
title: 建立您的歷程報告
description: 瞭解如何建立歷程報告
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
source-git-commit: b87de729f48c4624554eb19b6d418cb3cf70b805
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 2%

---


# 建立您的歷程報告 {#concept_rfj_wpt_52b}

## 存取和建立報表 {#accessing-reports}

>[!NOTE]
>
>刪除歷程後，將無法再使用所有相關的報表。

本節將介紹如何建立或使用現成可用的報告。 結合面板、元件和視覺化，以更好地追蹤您的歷程。

若要存取您的歷程報表並開始追蹤傳送的成功：

1. 在頂端選單中，按一下「**[!UICONTROL Home]**」標籤。

1. 選擇您要報告的歷程。

   請注意，您也可以按一下「報表」 **** ，將滑鼠暫留在歷程清單中的歷程上，以存取您的報表。

   ![](../assets/dynamic_report_journey.png)

1. 按一下 **[!UICONTROL Report]** 螢幕右上方的圖示。

   ![](../assets/dynamic_report_journey_2.png)

1. 熒 **[!UICONTROL Journey summary]** 幕上會顯示現成可用的報表。 若要存取自訂報表，請按一下 **[!UICONTROL Close]** 按鈕。

   ![](../assets/dynamic_report_journey_12.png)

1. 按一下 **[!UICONTROL Create new project]** 以從頭開始建立報表。

   ![](../assets/dynamic_report_journey_3.png)

1. 從標籤 **[!UICONTROL Panels]** 中，視需要拖放任意數量的面板或自由表格。 For more information, refer to this [section](#adding-panels).

   ![](../assets/dynamic_report_journey_4.png)

1. 然後，您可以從標籤拖放維度和量度至自由表格，開始 **[!UICONTROL Components]** 篩選資料。 For more information, refer to this [section](#adding-components).

   ![](../assets/dynamic_report_journey_5.png)

1. 若要更清楚地檢視您的資料，您可以從標籤中新增視覺 **[!UICONTROL Visualizations]** 化。 For more information, refer to this [section](#adding-visualizations).

## 新增面板{#adding-panels}

### 新增空白麵板 {#adding-a-blank-panel}

若要啟動報表，您可以新增一組面板至現成可用的或自訂報表。 每個面板包含不同的資料集，由自由表格和視覺化組成。

此面板可讓您視需要建立報表。 您可以在報表中新增任意數量的面板，以便以不同的時段來篩選資料。

1. 按一下 **[!UICONTROL Panels]** 圖示。 您也可以按一下並選取，以新增 **[!UICONTROL Insert tab]** 面板 **[!UICONTROL New Blank Panel]**。

   ![](../assets/dynamic_report_panel_1.png)

1. 拖放至控 **[!UICONTROL Blank Panel]** 制面板。

   ![](../assets/dynamic_report_panel.png)

您現在可以新增自由表格至面板，以開始定位資料。

### 新增自由表格 {#adding-a-freeform-table}

自由表格可讓您建立表格，以使用表格中可用的不同度量和維度來分析 **[!UICONTROL Component]** 資料。

每個表格和視覺化都可調整大小，並可加以移動，以更好地自訂您的報表。

1. 按一下 **[!UICONTROL Panels]** 圖示。

   ![](../assets/dynamic_report_panel_1.png)

1. 將項目拖放 **[!UICONTROL Freeform]** 至控制面板。

   您也可以按一下標籤並選取或按一 **[!UICONTROL Insert]** 下空白麵板， **[!UICONTROL New Freeform]** 以新增 **[!UICONTROL Add a freeform table]** 表格。

   ![](../assets/dynamic_report_panel_2.png)

1. 將標籤中的項目 **[!UICONTROL Components]** 拖放至欄和列，以建立表格。

   ![](../assets/dynamic_report_freeform_3.png)

1. 按一下 **[!UICONTROL Settings]** 圖示，變更資料在欄中的顯示方式。

   ![](../assets/dynamic_report_freeform_4.png)

   其組 **[!UICONTROL Column settings]** 成包括：

   * **[!UICONTROL Number]**: 可讓您顯示或隱藏欄中的摘要數字。
   * **[!UICONTROL Percent]**: 可讓您顯示或隱藏欄中的百分比。
   * **[!UICONTROL Interpret zero as no value]**: 可讓您在值等於零時顯示或隱藏。
   * **[!UICONTROL Background]**: 可讓您顯示或隱藏儲存格中的水準進度列。
   * **[!UICONTROL Include retries]**: 可讓您在結果中包含重試。 這僅適用於 **[!UICONTROL Sent]** 和 **[!UICONTROL Bounces + Errors]**。

1. 選取一或多列，然後按一下圖 **[!UICONTROL Visualize]** 示。 會新增視覺化以反映您選取的列。

   ![](../assets/dynamic_report_freeform_5.png)

您現在可以視需要新增多個元件，並新增視覺化，以提供資料的圖形表示。

## 新增元件{#adding-components}

元件可協助您使用不同的維度、量度和時段自訂報表。

1. 按一下 **[!UICONTROL Components]** 標籤以存取元件清單。

   ![](../assets/dynamic_report_components.png)

1. 標籤中顯示的每 **[!UICONTROL Components]** 個類別都會顯示五個最常使用的項目，請按一下類別名稱以存取其完整的元件清單。

   元件表分為三類：

   * **[!UICONTROL Dimensions]**: 從傳送記錄檔取得詳細資訊，例如收件者的瀏覽器或網域，或傳送成功。
   * **[!UICONTROL Metrics]**: 取得訊息狀態的詳細資訊。 例如，如果傳送訊息，且使用者將其開啟。
   * **[!UICONTROL Time]**: 設定表格的時段。

1. 在面板中拖放元件，開始篩選資料。

您可以視需要拖放多個元件，並將它們彼此比較。

## 新增視覺效果{#adding-visualizations}

標籤 **[!UICONTROL Visualizations]** 可讓您拖放視覺化項目，例如區域、環圈和圖形。 視覺化可提供資料的圖形表示。

1. 在標籤 **[!UICONTROL Visualizations]** 中，拖放面板中的視覺化項目。

   ![](../assets/dynamic_report_visualization_1.png)

1. 將視覺化新增至面板後，您的報表會自動偵測自由表格中的資料。 選取視覺化的設定。
1. 如果您有多個自由表格，請在視窗中選擇要新增至圖形中的可用資料來源 **[!UICONTROL Data Source Settings]** 。 按一下視覺化標題旁的彩色點，也可使用此視窗。

   ![](../assets/dynamic_report_visualization_2.png)

1. 按一下 **[!UICONTROL Visualization]** 設定按鈕，直接變更圖形類型或圖形上顯示的項目，例如：

   * **[!UICONTROL Percentages]**: 以百分比顯示值。
   * **[!UICONTROL Anchor Y Axis at Zero]**: 即使值範圍超過零，也強制y軸為零。
   * **[!UICONTROL Legend visible]**: 可讓您隱藏圖例。
   * **[!UICONTROL Normalization]**: 強制值相符。
   * **[!UICONTROL Display Dual Axis]**: 將另一個軸添加到圖形中。
   * **[!UICONTROL Limit Max Items]**: 限制顯示的圖形數。
   * **[!UICONTROL Threshold]**: 可讓您設定圖形的臨界值。 它看起來像黑色的虛線。

   ![](../assets/dynamic_report_visualization_3.png)

此視覺化功能可讓您更清楚地檢視報表中的資料。