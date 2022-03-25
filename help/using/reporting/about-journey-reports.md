---
product: adobe campaign
title: 關於歷程報告
description: 瞭解如何構建行程報告
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
>只有在您具有Adobe Campaign Standard時，才會填充交付資料和段元件。

本節將介紹如何訪問和使用報告來衡量您的旅程的有效性。

## 報告介面 {#reporting-interface}

例如，頂部工具欄允許您修改、保存或打印報表。

![](../assets/dynamic_report_toolbar.png)

使用 **[!UICONTROL Project]** 頁籤：

* **[!UICONTROL Open]**:開啟以前建立的報告或模板。
* **[!UICONTROL Save As]**:複製模板以便能夠修改它們。
* **[!UICONTROL Refresh project]**:根據新資料和對篩選器的更改更新報告。
* **[!UICONTROL Download CSV]**:將報告導出為CSV檔案。
* **[!UICONTROL Print]**:打印報告。

的 **[!UICONTROL Edit]** 頁籤

* **[!UICONTROL Undo]**:取消儀表板上的上一操作。
* **[!UICONTROL Redo]**:取消上次 **[!UICONTROL Undo]** 操作。
* **[!UICONTROL Clear all]**:刪除儀表板上的每個面板。

的 **[!UICONTROL Insert]** 表：通過將圖形和表添加到面板來定制報表：

* **[!UICONTROL New Blank Panel]**:將新的空白麵板添加到儀表板。
* **[!UICONTROL New Freeform]**:將新的自由形式表格添加到操控板。
* **[!UICONTROL New Line]**:將新線形圖添加到儀表板。
* **[!UICONTROL New Bar]**:將新條形圖添加到儀表板。

左側的頁籤允許您生成報告並根據需要篩選資料。

![](../assets/dynamic_report_interface.png)

這些頁籤允許您訪問以下項目：

* **[!UICONTROL Panels]**:將空白麵板或自由格式添加到報表以開始篩選資料。 有關詳細資訊，請參閱 [添加面板](../reporting/creating-your-journey-reports.md#adding-panels) 節
* **[!UICONTROL Visualizations]**:拖放選定的可視化項目，為報表提供圖形尺寸。 有關詳細資訊，請參閱 [添加可視化效果](../reporting/creating-your-journey-reports.md#adding-visualizations) 的子菜單。
* **[!UICONTROL Components]**:使用不同的維度、度量、段和時段自定義報表。 有關詳細資訊，請參閱 [添加元件](../reporting/creating-your-journey-reports.md#adding-components) 的子菜單。

## 行程摘要模板 {#ootb-template}

報告分為兩類：現成模板和自定義報告。
現成模板， **[!UICONTROL Journey summary]**，可以清楚地查看最重要的跟蹤資料。

![](../assets/dynamic_report_journey_8.png)

每個表都由摘要數字和圖表表示。 您可以更改詳細資訊在其各自的可視化設定中的顯示方式。

以下KPI可在報表頂部使用：

* **[!UICONTROL Journey - Entered]**:到達旅程的入門事件的個人總數。
* **[!UICONTROL Journey - Completion rate]**:到達行程終點的個人總數（或當個人不符合任何條件時）與進入行程的個人總數之比。
* **[!UICONTROL Journey - Current]**:當前在旅途中的個人總數。
* **[!UICONTROL Journey - Failed rate]**:未成功執行的行程總數與運行行程總數相比。
* **[!UICONTROL Delivery - Messages sent]**:發送的消息總數。
* **[!UICONTROL Delivery rate]**:與發送的消息相比，成功傳遞的消息總數。
* **[!UICONTROL Delivery - Bounce rate]**:與發送的消息相比，跳轉的消息總數。
* **[!UICONTROL Delivery - Unsubscribed rate]**:與已傳遞郵件相比，收件人未訂閱的總數。
* **[!UICONTROL Delivery - Open rate]**:與已傳遞郵件數相比，已開啟郵件總數。
* **[!UICONTROL Delivery - Click rate]**:傳遞中的點擊總數與傳遞的郵件數相比。

Journey流可視化允許您逐步查看目標配置檔案的路徑。 這隻適用於一次行程。 它是自動生成的，無法修改。

![](../assets/dynamic_report_journey_10.png)

的 **[!UICONTROL Journey summary]** 表包含可用於行程的資料，例如：

* **[!UICONTROL Entered]**:到達旅程的入門事件的個人總數。
* **[!UICONTROL Completion rate]**:到達行程的最終流控制的個人總數，與進入行程的個人總數相比。
* **[!UICONTROL Current]**:當前在旅途中的個人總數。
* **[!UICONTROL Failed]**:未成功執行的行程總數。
* **[!UICONTROL Failed rate]**:未成功執行的行程總數與運行行程總數相比。

的 **[!UICONTROL Top events]** 表顯示最成功的事件， **[!UICONTROL Top action]**&#x200B;是你旅途中最成功的行動。

![](../assets/dynamic_report_journey_11.png)

的 **[!UICONTROL Delivery - Sending summary]** 表包含可用於行程交貨的資料，例如：

* **[!UICONTROL Processed/sent]**:發送的消息總數。
* **[!UICONTROL Delivered rate]**:與發送的消息相比，成功傳遞的消息總數。
* **[!UICONTROL Delivered]**:成功發送的消息數，與已發送的消息總數相關。
* **[!UICONTROL Bounce + error rate]**:與發送的消息相比，跳轉的消息總數。
* **[!UICONTROL Bounces + errors]**:在傳遞和自動返回處理期間累積的與已發送消息總數有關的錯誤總數。

的 **[!UICONTROL Delivery - Tracking summary]** 表包含用於跟蹤您的行程交付成功的資料，例如：

* **[!UICONTROL Open Rate]**:已開啟郵件的百分比。
* **[!UICONTROL Open]**:在傳遞中開啟消息的次數。
* **[!UICONTROL Click trough rate]**:傳遞中的點擊總數與傳遞的郵件數相比。
* **[!UICONTROL Click]**:在傳遞中按一下內容的次數。
* **[!UICONTROL Unsubscribe rate]**:接收方未訂閱與已傳遞郵件的百分比。
* **[!UICONTROL Unsubscribed]**:與已傳遞郵件相比，收件人未訂閱的總數。
