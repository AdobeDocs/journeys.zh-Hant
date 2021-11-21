---
product: adobe campaign
title: 關於歷程報告
description: 了解如何建立歷程報告
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
>只有在您有Adobe Campaign Standard時，才會填入傳送資料和區段元件。

本節將說明如何存取和使用報告來評估您歷程的成效。

## 報告介面 {#reporting-interface}

例如，頂端工具列可讓您修改、儲存或列印報表。

![](../assets/dynamic_report_toolbar.png)

使用 **[!UICONTROL Project]** 頁簽到：

* **[!UICONTROL Open]**:開啟先前建立的報表或範本。
* **[!UICONTROL Save As]**:複製範本，以便修改範本。
* **[!UICONTROL Refresh project]**:會根據新資料和篩選條件變更來更新報表。
* **[!UICONTROL Download CSV]**:將報表匯出為CSV檔案。
* **[!UICONTROL Print]**:打印報告。

此 **[!UICONTROL Edit]** 頁簽，您可以：

* **[!UICONTROL Undo]**:取消控制面板上的最後一個動作。
* **[!UICONTROL Redo]**:取消了 **[!UICONTROL Undo]** 動作。
* **[!UICONTROL Clear all]**:刪除控制面板上的每個面板。

此 **[!UICONTROL Insert]** 表格可讓您將圖形和表格新增至控制面板，借此自訂報表：

* **[!UICONTROL New Blank Panel]**:將新的空白麵板新增至控制面板。
* **[!UICONTROL New Freeform]**:新增自由表格至控制面板。
* **[!UICONTROL New Line]**:將新折線圖新增至控制面板。
* **[!UICONTROL New Bar]**:將新的長條圖新增至控制面板。

左側標籤可讓您建立報表，並視需要篩選資料。

![](../assets/dynamic_report_interface.png)

這些標籤可讓您存取下列項目：

* **[!UICONTROL Panels]**:新增空白麵板或自由格式至報表，以開始篩選資料。 有關詳細資訊，請參閱 [新增面板](../reporting/creating-your-journey-reports.md#adding-panels) 節
* **[!UICONTROL Visualizations]**:拖放選取的視覺效果項目，為報表提供圖形維度。 有關詳細資訊，請參閱 [新增視覺效果](../reporting/creating-your-journey-reports.md#adding-visualizations) 區段。
* **[!UICONTROL Components]**:使用不同的維度、量度、區段和時段自訂報表。 有關詳細資訊，請參閱 [新增元件](../reporting/creating-your-journey-reports.md#adding-components) 區段。

## 歷程摘要範本 {#ootb-template}

報表分為兩個類別：現成可用的範本和自訂報表。
現成的範本， **[!UICONTROL Journey summary]**，可讓您清楚檢視最重要的追蹤資料。

![](../assets/dynamic_report_journey_8.png)

每個表由摘要數字和圖表表示。 您可以變更詳細資料在其個別視覺效果設定中的顯示方式。

報表頂端提供下列KPI:

* **[!UICONTROL Journey - Entered]**:到達歷程進入事件的個人總數。
* **[!UICONTROL Journey - Completion rate]**:達到歷程結束的個人總數（或當個人不符合任何條件時），與進入歷程的個人總數相比較。
* **[!UICONTROL Journey - Current]**:目前在歷程中的個人總數。
* **[!UICONTROL Journey - Failed rate]**:與執行歷程次數相比，未成功執行的歷程總數。
* **[!UICONTROL Delivery - Messages sent]**:已傳送的訊息總數。
* **[!UICONTROL Delivery rate]**:與已傳送的訊息相比，已成功傳送的訊息總數。
* **[!UICONTROL Delivery - Bounce rate]**:與已傳送的訊息相比，已跳出的訊息總數。
* **[!UICONTROL Delivery - Unsubscribed rate]**:收件者與已傳送訊息相比的取消訂閱總數。
* **[!UICONTROL Delivery - Open rate]**:與已傳送訊息數相比，已開啟訊息的總數。
* **[!UICONTROL Delivery - Click rate]**:傳遞中的點按總次數與已傳遞訊息的次數比較。

歷程流量視覺效果可讓您逐步查看目標設定檔的路徑。 這僅適用於定位一個歷程時。 系統會自動產生，且無法修改。

![](../assets/dynamic_report_journey_10.png)

此 **[!UICONTROL Journey summary]** 表格包含您歷程的可用資料，例如：

* **[!UICONTROL Entered]**:到達歷程進入事件的個人總數。
* **[!UICONTROL Completion rate]**:達到歷程的結束流量控制的個人總數，與進入歷程的個人總數相比。
* **[!UICONTROL Current]**:目前在歷程中的個人總數。
* **[!UICONTROL Failed]**:未成功執行的歷程總數。
* **[!UICONTROL Failed rate]**:與執行歷程次數相比，未成功執行的歷程總數。

此 **[!UICONTROL Top events]** 表格會顯示最成功的事件，而 **[!UICONTROL Top action]**，是您歷程中最成功的動作。

![](../assets/dynamic_report_journey_11.png)

此 **[!UICONTROL Delivery - Sending summary]** 表格包含可用於歷程傳送的資料，例如：

* **[!UICONTROL Processed/sent]**:已傳送的訊息總數。
* **[!UICONTROL Delivered rate]**:與已傳送的訊息相比，已成功傳送的訊息總數。
* **[!UICONTROL Delivered]**:已成功傳送的訊息數，與已傳送的訊息總數相關。
* **[!UICONTROL Bounce + error rate]**:與已傳送的訊息相比，已跳出的訊息總數。
* **[!UICONTROL Bounces + errors]**:與已傳送訊息總數相關的傳送和自動回傳處理期間累積的錯誤總數。

此 **[!UICONTROL Delivery - Tracking summary]** 表格包含可用於追蹤歷程傳送成功的資料，例如：

* **[!UICONTROL Open Rate]**:已開啟訊息的百分比。
* **[!UICONTROL Open]**:傳送中開啟訊息的次數。
* **[!UICONTROL Click trough rate]**:傳遞中的點按總次數與已傳遞訊息的次數比較。
* **[!UICONTROL Click]**:內容在傳送中被點按的次數。
* **[!UICONTROL Unsubscribe rate]**:收件者取消訂閱與已傳送訊息的百分比。
* **[!UICONTROL Unsubscribed]**:收件者與已傳送訊息相比的取消訂閱總數。
