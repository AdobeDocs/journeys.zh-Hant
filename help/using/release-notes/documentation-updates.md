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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 71b5b1ecd20056d0103ae1a8b83a31478449e844
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 51%

---


# 文件更新

This page lists all the documentation updates for [!DNL Journey Orchestration].
You can also consult the [!DNL Journey Orchestration] [Release Notes](../release-notes/release-notes.md).

## 2020 年 7 月{#july-2020}

* 已新增連結至新的教學課程影片，說明Adobe Experience Platform的步驟事件報告。 [瞭解詳情](../building-journeys/sharing-overview.md)
* 事件活動區段已重新組織為每種事件類型的專屬子區段。 [瞭解詳情](../building-journeys/event-activities.md)
* 已新增最佳實務，以避免區段品質過載。 [瞭解詳情](../building-journeys/segment-qualification-events.md#speed-segment-qualification)
* 已新增附註，說明如何在動作或條件發生錯誤後讓旅程繼續。 [瞭解詳情](../about/troubleshooting.md#section_h3q_kqk_fhb)
* 已新增Alpha功能的章節，這些功能會在有限的客戶群中進行測試。 [瞭解詳情](../alpha/alpha-overview.md)
* 已新增與智慧型服務整合的章節。 [瞭解詳情](../ai-services/ai-services-overview.md)
* 已新增測試描述檔建立的新區段。 [瞭解詳情](../building-journeys/testing-the-journey.md#create-test-profile)
* 已新增如何在歷程條 **[!UICONTROL SegmentQualification]** 件或動作中使用節點的資訊。 [瞭解詳情](../building-journeys/segment-qualification-events.md)
* 已在促銷活動交易訊息和事件發佈中新增附註。 請參 [閱使用Adobe Campaign](../action/working-with-adobe-campaign.md)[和使用Adobe Campaign動作](../building-journeys/using-adobe-campaign-actions.md)。
* 已新增資訊至測試「促銷活動標準」例項URL時所執行的檢查。 [瞭解詳情](../action/working-with-adobe-campaign.md)
* 已新增有關與AWS或Azure伺服器上裝載的Campaign Standard例項相容的反應事件資訊。 [瞭解詳情](../building-journeys/reaction-events.md)
* 已新增附註，說明使用「促銷活動標準」交易訊息時需要設定上限規則。 [瞭解詳情](../action/working-with-adobe-campaign.md)
* 使用測試模式觸發事件時，產生實際事件時已新增附註。 [瞭解詳情](../building-journeys/testing-the-journey.md#firing_events)

## 2020 年 6 月 {#june-2020}

* 已新增有關如何變更自訂驗證資料來源之Token的快取持續時間的資訊。 [瞭解詳情](../datasource/external-data-sources.md#section_wjp_nl5_nhb)
* 更新螢幕擷取畫面和文字，以反映已變 **[!UICONTROL Finished]** 更為的歷程狀態重新命名 **[!UICONTROL Closed (no entrance)]**。
* 已新增如何為介面定義語言的資訊。 [瞭解詳情](../about/user-interface.md)
* 個人歷程的狀態清單已移至「測試模式記錄 [」區段](../building-journeys/testing-the-journey.md#viewing_logs) 。

## 2020 年 4 月{#april-2020}

* 已新增體驗事件結構定義的新區段，以協助使用者設定其第一個事件。 [瞭解詳情](../event/experience-event-schema.md)
* 檔案的首頁已 [!DNL Journey Orchestration] 經更新，提供其他有用的連結。 [瞭解詳情](../../journey-orchestration-home.md)

## 2020 年 3月{#march-2020}

* 已新增測試記錄區段中 _actionExecutionErrors_ 和 _fetchErrors_ 的參數說明。[詳細內容](../building-journeys/testing-the-journey.md#viewing_logs)
* 已更新歷程中使用的自訂動作限制。You can also modify the **[!UICONTROL URL]** field and the **[!UICONTROL Authentication]** parameters. [詳細內容](../action/about-custom-action-configuration.md)
* 已新增內容說明項目。自訂驗證裝載窗格 (在動作和資料來源中) 現已包含連結至此[章節](../datasource/external-data-sources.md#section_wjp_nl5_nhb)的說明圖示。
* 現在可以停止封閉的旅程。 [詳細內容](../building-journeys/using-the-journey-designer.md)
* 已重新組織介面說明章節。[詳細內容](../about/user-interface.md)
* 已將多個事件的觸發條件新增至「測試模式」章節[詳細內容](../building-journeys/testing-the-journey.md#firing_events)
* 「測試模式」區段已更新，與新參 **[!UICONTROL Wait time in test]** 數有關。 [詳細內容](../building-journeys/testing-the-journey.md)
* 已更新「測試記錄」章節的外部呼叫錯誤代碼和回應。[詳細內容](../building-journeys/testing-the-journey.md#viewing_logs)
* 時區管理現已集中在歷程屬性面板中。詳細內容請見[此處](../building-journeys/changing-properties.md#timezone)和[此處](../building-journeys/timezone-management.md)
* 已更新「歷程設計器」章節以反映最近的增強功能。[詳細內容](../building-journeys/using-the-journey-designer.md)
* 已更新介面說明中內容說明的資訊。[詳細內容](../about/user-interface.md#section_ksq_zr1_ffb)
* 瀏覽 **XDM 欄位**&#x200B;時現在會顯示好記的名稱。已更新相關章節。[詳細內容](../about/user-interface.md#friendly-names-display)

## 2020 年 2 月{#february-2020}

* 已更新快速鍵章節。**C** 鍵盤快速鍵可讓您在所有清單畫面中建立新項目。[詳細內容](../about/user-interface.md#section_ksq_zr1_ffb)
* 資料 [來源](../datasource/about-data-sources.md)[和動作概](../action/action.md) 述頁面已改良。

## 2020 年 1 月{#january-2020}

* 已在[體驗事件](../datasource/adobe-experience-platform-data-source.md)和[區段](../functions/functioninsegment.md)新增擷取限制。
* 已更新 [getBestSendTime documentation](../functions/functiongetbestsendtime.md)。

## 2019 年 12 月{#december-2019}

* 已更新所有螢幕擷取畫面以反映介面的變更。
* 已更新測試模式章節。[詳細內容](../building-journeys/testing-the-journey.md)
* 已在[電子郵件傳送時間最佳化](../building-journeys/wait-activity.md)和[可預測的疲勞分數](../ai-services/leveraging-fatigue-scores.md)章節新增警告。這些功能僅適用於使用 Adobe Campaign Standard 資料服務功能的客戶。
* 現在可刪除已停止的歷程。已更新相關文件頁面。
* 在歷程中偵測到問題時，現在會顯示兩種顏色。紅色代表錯誤，橘色代表警告。[詳細內容](../about/troubleshooting.md)
* 已更新進階運算式編輯器章節。[詳細內容](../expression/expressionadvanced.md)。
* 已移動和更新[條件式指令](../expression/conditional-instruction.md)和[系列管理](../expression/collection-management-functions.md)章節。
* 已在[函式](../expression/functions.md)章節新增新的範例。
* 已更新 [toDateTime 函式](../functions/functiontodatetime.md)文件以反映時區語法的變更。
