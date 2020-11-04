---
title: 文件更新
description: 瞭解文件更新
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: fe51a1600050a42c2070ad78f14490ea1813bd14
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 94%

---


# 文件更新

本頁面列出 [!DNL Journey Orchestration] 的所有文件更新。您也可以參閱[!DNL Journey Orchestration][發行說明](../release-notes/release-notes.md)。

## 2020 年 10 月 {#october-2020}

* 已新增有關如何設定事件逾時的資訊。 [顯示全文](../building-journeys/event-activities.md#listening-to-events-during-a-specific-time)。

## 2020 年 9 月{#september-2020}

* 已更新介面說明區段，以反映新的「全 **部選取器** 」功能表。 [顯示全文](../about/user-interface.md)
* 已新增非經常性區段型歷程新版本的附註。 [顯示全文](../alpha/alpha-segment-trigger.md)

## 2020 年 8 月{#august-2020}

* 已新增關於如何排序以及選擇要在區段清單中顯示欄的資訊。[顯示全文](../building-journeys/segment-qualification-events.md)
* 已新增關於在選取區段後如何複製區段名稱及 ID 的資訊。[顯示全文](../building-journeys/segment-qualification-events.md)
* 已在不同頁面上協調 Experience Platform 的發生次數。

## 2020 年 7 月{#july-2020}

* 已新增新教學課程影片的連結，其中說明向 Adobe Experience Platform 報告事件的步驟。[顯示全文](../building-journeys/sharing-overview.md)
* 以針對每種類型的事件，將事件活動區段重新組織到專屬子區段。[顯示全文](../building-journeys/event-activities.md)
* 已新增最佳實務，以避免區段資格過載。[顯示全文](../building-journeys/segment-qualification-events.md#speed-segment-qualification)
* 已新增附註，說明在動作或條件發生錯誤後，如何讓歷程繼續。[顯示全文](../about/troubleshooting.md#section_h3q_kqk_fhb)
* 已新增 Alpha 功能的區段，這些功能會在有限的客戶群中進行測試。[詳細內容](../alpha/alpha-overview.md)
* 已新增與智慧型服務整合的區段。[詳細內容](../ai-services/ai-services-overview.md)
* 已新增測試設定檔建立的區段。[詳細內容](../building-journeys/testing-the-journey.md#create-test-profile)
* 已新增如何在歷程條件或動作中使用 **[!UICONTROL SegmentQualification]** 節點的資訊。[詳細內容](../building-journeys/segment-qualification-events.md)
* 已在 Campaign 交易訊息及事件發佈中新增附註。請參閱[使用 Adobe Campaign ](../action/working-with-adobe-campaign.md)及[使用 Adobe Campaign 動作](../building-journeys/using-adobe-campaign-actions.md)。
* 已新增對於檢查的資訊，這些檢查會在測試 Campaign Standard 執行個體 URL 時執行。[詳細內容](../action/working-with-adobe-campaign.md)
* 已新增反應事件相容性的資訊，而且會在 AWS 或 Azure 伺服器上託管 Campaign Standard 執行個體。[詳細內容](../building-journeys/reaction-events.md)
* 在使用 Campaign Standard 交易訊息時，已針對設定上限規則的需求新增附註。[詳細內容](../action/working-with-adobe-campaign.md)
* 使用測試模式觸發事件時，已針對產生真實事件新增附註。[詳細內容](../building-journeys/testing-the-journey.md#firing_events)

## 2020 年 6 月 {#june-2020}

* 已新增如何針對自訂驗證資料來源變更權杖的快取期間的資訊。[詳細內容](../datasource/external-data-sources.md#section_wjp_nl5_nhb)
* 以更新螢幕擷取畫面及文字，以反映重新命名 **[!UICONTROL Finished]** 歷程狀態（其已變更為 **[!UICONTROL Closed (no entrance)]**)。
* 已新增如何為介面定義語言的資訊。[詳細內容](../about/user-interface.md)
* 個人歷程的狀態清單已移至[測試模式記錄](../building-journeys/testing-the-journey.md#viewing_logs)區段。

## 2020 年 4 月{#april-2020}

* 已新增體驗事件綱要的新區段，以協助使用者設定其第一個事件。[詳細內容](../event/experience-event-schema.md)
* [!DNL Journey Orchestration]　文件的首頁已經更新，且包含其他實用連結。[詳細內容](../../journey-orchestration-home.md)

## 2020 年 3 月{#march-2020}

* 已新增測試記錄區段中 _actionExecutionErrors_ 和 _fetchErrors_ 的參數說明。[詳細內容](../building-journeys/testing-the-journey.md#viewing_logs)
* 已更新歷程中使用的自訂動作限制。您也可以修改 **[!UICONTROL URL]** 欄位和 **[!UICONTROL Authentication]** 參數。[詳細內容](../action/about-custom-action-configuration.md)
* 已新增內容說明項目。自訂驗證裝載窗格 (在動作和資料來源中) 現已包含連結至此[章節](../datasource/external-data-sources.md#section_wjp_nl5_nhb)的說明圖示。
* 現在可以停止已關閉的歷程。[詳細內容](../building-journeys/using-the-journey-designer.md)
* 已重新組織介面說明章節。[詳細內容](../about/user-interface.md)
* 已將多個事件的觸發條件新增至「測試模式」章節[詳細內容](../building-journeys/testing-the-journey.md#firing_events)
* 與新的 **[!UICONTROL Wait time in test]** 參數相關的「測試」模式區段已更新。[詳細內容](../building-journeys/testing-the-journey.md)
* 已更新「測試記錄」章節的外部呼叫錯誤代碼和回應。[詳細內容](../building-journeys/testing-the-journey.md#viewing_logs)
* 時區管理現已集中在歷程屬性面板中。詳細內容請見[此處](../building-journeys/changing-properties.md#timezone)和[此處](../building-journeys/timezone-management.md)
* 已更新「歷程設計器」章節以反映最近的增強功能。[詳細內容](../building-journeys/using-the-journey-designer.md)
* 已更新介面說明中內容說明的資訊。[詳細內容](../about/user-interface.md#section_ksq_zr1_ffb)
* 瀏覽 **XDM 欄位**&#x200B;時現在會顯示好記的名稱。已更新相關章節。[詳細內容](../about/user-interface.md#friendly-names-display)

## 2020 年 2 月{#february-2020}

* 已更新快速鍵章節。**C** 鍵盤快速鍵可讓您在所有清單畫面中建立新項目。[詳細內容](../about/user-interface.md#section_ksq_zr1_ffb)
* [資料來源](../datasource/about-data-sources.md)及[動作](../action/action.md)概述頁面已經過改良。

## 2020 年 1 月{#january-2020}

* 已在[體驗事件](../datasource/adobe-experience-platform-data-source.md)及[區段](../functions/functioninsegment.md)新增擷取限制。

<!--* The [getBestSendTime documentation](../functions/functiongetbestsendtime.md) has been updated.-->

## 2019 年 12 月{#december-2019}

* 已更新所有螢幕擷取畫面以反映介面的變更。
* 已更新測試模式章節。[詳細內容](../building-journeys/testing-the-journey.md)
<!--* A warning has been added in the [email send time optimization](../building-journeys/wait-activity.md) and [predictive fatigue scores](../ai-services/leveraging-fatigue-scores.md) sections. These capabilities are only available to customers who use the [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html).-->
* 現在可刪除已停止的歷程。已更新相關文件頁面。
* 在歷程中偵測到問題時，現在會顯示兩種顏色。紅色代表錯誤，橘色代表警告。[詳細內容](../about/troubleshooting.md)
* 已更新進階運算式編輯器章節。[詳細內容](../expression/expressionadvanced.md)。
* 已移動和更新[條件式指令](../expression/conditional-instruction.md)和[系列管理](../expression/collection-management-functions.md)章節。
* 已在[函式](../expression/functions.md)章節新增新的範例。
* 已更新 [toDateTime 函式](../functions/functiontodatetime.md)文件以反映時區語法的變更。
