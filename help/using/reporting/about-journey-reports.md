---
product: adobe campaign
title: 關於歷程報告
description: 瞭解如何建立您的歷程報告
feature: Journeys
role: User
level: Intermediate
exl-id: 93768321-b171-4338-a440-6ea189a85a4a
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 1%

---

# 關於歷程報告 {#concept_rfj_wpt_52b}

>[!NOTE]
>
>只有在您有Adobe Campaign Standard的情況下，才會填入傳遞資料和區段元件。

本節將說明如何存取及使用報表來評估歷程的成效。

## 報告介面 {#reporting-interface}

例如，頂端工具列可讓您修改、儲存或列印報告。

![](../assets/dynamic_report_toolbar.png)

使用&#x200B;**[!UICONTROL Project]**&#x200B;標籤可以：

* **[!UICONTROL Open]**：開啟先前建立的報表或範本。
* **[!UICONTROL Save As]**：重複範本以便修改。
* **[!UICONTROL Refresh project]**：根據新資料和篩選器變更來更新您的報告。
* **[!UICONTROL Download CSV]**：將報表匯出至CSV檔案。
* **[!UICONTROL Print]**：列印您的報告。

**[!UICONTROL Edit]**&#x200B;索引標籤可讓您：

* **[!UICONTROL Undo]**：取消您在上一個儀表板上的動作。
* **[!UICONTROL Redo]**：取消您的儀表板上的最後&#x200B;**[!UICONTROL Undo]**&#x200B;個動作。
* **[!UICONTROL Clear all]**：刪除您控制面板上的每個面板。

**[!UICONTROL Insert]**&#x200B;表格可讓您新增圖形和表格至您的儀表板，以自訂報表：

* **[!UICONTROL New Blank Panel]**：將新的空白面板新增至您的儀表板。
* **[!UICONTROL New Freeform]**：將新的自由表格新增至您的儀表板。
* **[!UICONTROL New Line]**：新增線條圖至您的儀表板。
* **[!UICONTROL New Bar]**：將新的長條圖新增至您的儀表板。

左邊標籤可讓您建立報告，並依需求篩選資料。

![](../assets/dynamic_report_interface.png)

這些標籤可讓您存取以下專案：

* **[!UICONTROL Panels]**：新增空白面板或自由格式至您的報告，以開始篩選您的資料。 如需詳細資訊，請參閱[新增面板](../reporting/creating-your-journey-reports.md#adding-panels)區段
* **[!UICONTROL Visualizations]**：拖放選取的視覺效果專案，讓您的報表具有圖形維度。 如需詳細資訊，請參閱[新增視覺效果](../reporting/creating-your-journey-reports.md#adding-visualizations)區段。
* **[!UICONTROL Components]**：使用不同的維度、量度、區段和時段來自訂您的報表。 如需詳細資訊，請參閱[新增元件](../reporting/creating-your-journey-reports.md#adding-components)區段。

## 歷程摘要範本 {#ootb-template}

報告分為兩個類別：現成可用的範本和自訂報告。
現成可用的範本**[!UICONTROL Journey summary]**&#x200B;可讓您清楚檢視最重要的追蹤資料。

![](../assets/dynamic_report_journey_8.png)

每個表格都由摘要數字和圖表表示。 您可以變更詳細資訊在其各自視覺效果設定中的顯示方式。

報表頂端提供下列KPI：

* **[!UICONTROL Journey - Entered]**：到達歷程進入事件的個人總數。
* **[!UICONTROL Journey - Completion rate]**：已到達歷程結束的個人總數（或如果個人不符合任何條件），與進入歷程的個人總數比較。
* **[!UICONTROL Journey - Current]**：目前歷程中的個人總數。
* **[!UICONTROL Journey - Failed rate]**：與執行歷程數相較之下，未成功執行的歷程總數。
* **[!UICONTROL Delivery - Messages sent]**：已傳送的訊息總數。
* **[!UICONTROL Delivery rate]**：與已傳送的訊息相比，已成功傳遞的訊息總數。
* **[!UICONTROL Delivery - Bounce rate]**：與已傳送的訊息相比，退回的訊息總數。
* **[!UICONTROL Delivery - Unsubscribed rate]**：與傳遞的訊息相比，收件者的取消訂閱總數。
* **[!UICONTROL Delivery - Open rate]**：開啟的訊息總數與傳遞的訊息總數比較。
* **[!UICONTROL Delivery - Click rate]**：與已傳遞訊息數相較之下，傳遞中的點按總數。

歷程流量視覺效果可讓您在歷程中逐步檢視目標設定檔的路徑。 這僅在目標定位一個歷程時可用。 這會自動產生，且無法修改。

![](../assets/dynamic_report_journey_10.png)

**[!UICONTROL Journey summary]**&#x200B;表格包含您的歷程可用的資料，例如：

* **[!UICONTROL Entered]**：到達歷程進入事件的個人總數。
* **[!UICONTROL Completion rate]**：與進入歷程的個人總數相較之下，達到歷程結束流量控制的個人總數。
* **[!UICONTROL Current]**：目前歷程中的個人總數。
* **[!UICONTROL Failed]**：未成功執行的歷程總數。
* **[!UICONTROL Failed rate]**：與執行歷程數相較之下，未成功執行的歷程總數。

**[!UICONTROL Top events]**&#x200B;表格會顯示最成功的事件和&#x200B;**[!UICONTROL Top action]**，也就是您歷程中最成功的動作。

![](../assets/dynamic_report_journey_11.png)

**[!UICONTROL Delivery - Sending summary]**&#x200B;表格包含可用於您歷程傳遞的資料，例如：

* **[!UICONTROL Processed/sent]**：已傳送的訊息總數。
* **[!UICONTROL Delivered rate]**：與已傳送的訊息相比，已成功傳遞的訊息總數。
* **[!UICONTROL Delivered]**：成功傳送的訊息數，與已傳送的訊息總數相關。
* **[!UICONTROL Bounce + error rate]**：與已傳送的訊息相比，退回的訊息總數。
* **[!UICONTROL Bounces + errors]**：傳遞期間累計的錯誤總數，以及相對於已傳送訊息總數的自動傳回處理。

**[!UICONTROL Delivery - Tracking summary]**&#x200B;表格包含可用於追蹤歷程傳遞成功的資料，例如：

* **[!UICONTROL Open Rate]**：已開啟郵件的百分比。
* **[!UICONTROL Open]**：在傳遞中開啟郵件的次數。
* **[!UICONTROL Click trough rate]**：與已傳遞訊息數相較之下，傳遞中的點按總數。
* **[!UICONTROL Click]**：內容在傳遞中被點按的次數。
* **[!UICONTROL Unsubscribe rate]**：收件者的取消訂閱次數與傳遞的訊息相比的百分比。
* **[!UICONTROL Unsubscribed]**：與傳遞的訊息相比，收件者的取消訂閱總數。
