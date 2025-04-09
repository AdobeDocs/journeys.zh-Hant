---
product: adobe campaign
title: 文件更新
description: 瞭解文件更新
feature: Journeys
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: ac5d2cec-0b48-4863-afe3-19ac5f61c9fd
source-git-commit: 4f6c5f9326b4d1cc4a1a02a036b51e4ad1ae68c4
workflow-type: ht
source-wordcount: '992'
ht-degree: 100%

---

# 文件更新

本頁面列出 [!DNL Journey Orchestration] 所有文件更新。
您也可以參閱[!DNL Journey Orchestration][發行說明](../release-notes/release-notes.md)。

## 2022 年 7 月 {#july-2022}

* 歷程屬性的&#x200B;**輪廓時區**&#x200B;選項現在預設為停用。 [閱讀全文](../building-journeys/timezone-management.md#timezone-from-profiles)
* **等待**&#x200B;活動的&#x200B;**固定日期**&#x200B;選項不再提供。 [閱讀全文](../building-journeys/wait-activity.md)

## 2022 年 6 月 {#june-2022}

* 已新增查詢範例至此[頁面](../building-journeys/query-examples.md)

## 2022 年 3 月 {#march-2022}

* 在運算式編輯器中新增了如何加入運算式作為預設值的範例。[閱讀全文](../expression/field-references.md#default-value)

## 2022 年 2 月 {#feb-2022}

* 更新 [replace](../functions/functionreplace.md#example_2) 和 [replaceAll](../functions/functionreplaceall.md#example) 函式的說明頁面，其中包含有關目標參數的其他資訊和範例。
* 已在 [Operators](../expression/operators.md#important-notes) 頁面加入最佳做法。

## 2021 年 9 月

* 已更新下列函式頁面： [sethours](../functions/functionsethours.md)、[getListItem](../functions/functiongetlistitem.md)、[inSegment](../functions/functioninsegment.md)

* 已新增下列函式： [篩選](../functions/functionfilter.md)、[相交](../functions/functionintersect.md)、[toDateOnly](../functions/functiontodateonly.md)

* 已在運算式編輯器文件中新增 dateOnly 日期類型。 [閱讀全文](../expression/data-types.md)

* 新增自訂動作快取持續時間的詳細資料。 [閱讀更多](../datasource/external-data-sources.md#section_wjp_nl5_nhb)

* 已新增自訂動作預設連接埠的資訊。 [閱讀更多](../action/url-configuration.md)

* 新增在資料湖中查詢歷程步驟事件的常用範例。 [閱讀更多](../building-journeys/query-examples.md)

## 2021 年 8 月

* 更新具有動態 URL 路徑和動態標題之自訂動作的設定程式。 [閱讀全文](../action/url-configuration.md)
* 新增協助工具功能的相關章節。 [閱讀全文](../about/user-interface.md#accessibility)
* 新增區段評估方法的相關章節。 [閱讀全文](../segment/about-segments.md#evaluation-method-in-journey-orchestration)

## 2021 年 3 月 {#march-2021}

* 我們已詳細說明在 Adobe Experience Platform 中建立測試輪廓的完整流程。 [閱讀全文](../building-journeys/creating-test-profiles.md).

## 2021 年 1 月 {#january-2021}

* 新增在建立輪廓時觸發歷程的最佳做法。 [閱讀全文](../about/limitations.md#journeys-limitation-profile-creation).

## 2020 年 10 月 {#october-2020}

* 已新增有關如何設定事件逾時的資訊。 [閱讀全文](../building-journeys/event-activities.md#listening-to-events-during-a-specific-time).

## 2020 年 9 月 {#september-2020}

* 已更新介面說明章節，以反映新的&#x200B;**所有選取器**&#x200B;功能表。 [閱讀全文](../about/user-interface.md)
* 已新增非經常性之區段型歷程新版本的附註。

## 2020 年 8 月 {#august-2020}

* 已新增關於如何排序以及選擇要在區段清單中顯示欄的資訊。[閱讀全文](../building-journeys/segment-qualification-events.md)
* 已新增關於在選取區段後如何複製區段名稱及 ID 的資訊。[閱讀全文](../building-journeys/segment-qualification-events.md)
* 已在不同頁面上協調 Experience Platform 的發生次數。

## 2020 年 7 月 {#july-2020}

* 以針對每種類型的事件，將事件活動區段重新組織到專屬子區段。[閱讀全文](../building-journeys/event-activities.md)
* 已新增最佳做法，以避免細分資格篩選超載。[閱讀全文](../building-journeys/segment-qualification-events.md#speed-segment-qualification)
* 已新增附註，說明在動作或條件發生錯誤後，如何讓歷程繼續。[閱讀全文](../about/troubleshooting.md#section_h3q_kqk_fhb)
* 已新增 Alpha 功能的新章節，這些功能會在有限的客戶群中進行測試。
* 已新增與智慧型服務整合的區段。[閱讀全文](../ai-services/ai-services-overview.md)
* 已新增測試輪廓建立的區段。[閱讀全文](../building-journeys/testing-the-journey.md)
* 已新增如何在歷程條件或動作中使用 **[!UICONTROL SegmentQualification]** 節點的資訊。[閱讀全文](../building-journeys/segment-qualification-events.md)
* 已在 Campaign 交易訊息及事件發佈中新增附註。請參閱[使用 Adobe Campaign ](../action/working-with-adobe-campaign.md)及[使用 Adobe Campaign 動作](../building-journeys/using-adobe-campaign-actions.md)。
* 已新增對於檢查的資訊，這些檢查會在測試 Campaign Standard 執行個體 URL 時執行。[閱讀全文](../action/working-with-adobe-campaign.md)
* 已新增反應事件相容性的資訊，而且會在 AWS 或 Azure 伺服器上託管 Campaign Standard 執行個體。[閱讀全文](../building-journeys/reaction-events.md)
* 在使用 Campaign Standard 交易訊息時，已針對設定上限規則的需求新增附註。[閱讀全文](../action/working-with-adobe-campaign.md)
* 使用測試模式觸發事件時，已針對產生真實事件新增附註。[閱讀全文](../building-journeys/testing-the-journey.md#firing_events)

## 2020 年 6 月 {#june-2020}

* 已新增如何針對自訂驗證資料來源變更權杖的快取期間的資訊。[閱讀全文](../datasource/external-data-sources.md#section_wjp_nl5_nhb)
* 以更新螢幕擷取畫面及文字，以反映重新命名 **[!UICONTROL Finished]** 歷程狀態（其已變更為 **[!UICONTROL Closed (no entrance)]**)。
* 已新增如何為介面定義語言的資訊。[閱讀全文](../about/user-interface.md)
* 個人歷程的狀態清單已移至[測試模式記錄](../building-journeys/testing-the-journey.md#viewing_logs)區段。

## 2020 年 4 月 {#april-2020}

* 已新增體驗事件結構描述的新區段，以協助使用者設定其第一個事件。[閱讀全文](../event/experience-event-schema.md)
* [!DNL Journey Orchestration]文件的首頁已經更新，且包含其他實用連結。[閱讀全文](../../journey-orchestration-home.md)

## 2020 年 3 月 {#march-2020}

* 已新增測試記錄區段中 _actionExecutionErrors_ 和 _fetchErrors_ 的參數說明。[閱讀全文](../building-journeys/testing-the-journey.md#viewing_logs)
* 已更新歷程中使用的自訂動作限制。您也可以修改 **[!UICONTROL URL]** 欄位和 **[!UICONTROL Authentication]** 參數。[閱讀全文](../action/about-custom-action-configuration.md)
* 已新增新的內容說明項目。自訂驗證裝載窗格 (在動作和資料來源中) 現已包含連結至此[章節](../datasource/external-data-sources.md#section_wjp_nl5_nhb)的說明圖示。
* 現在可以停止已關閉的歷程。[閱讀全文](../building-journeys/using-the-journey-designer.md)
* 已重新組織介面說明章節。[閱讀全文](../about/user-interface.md)
* 已將多個事件的觸發條件新增至「測試模式」章節[詳細內容](../building-journeys/testing-the-journey.md#firing_events)
* 與新的 **[!UICONTROL Wait time in test]** 參數相關的「測試」模式區段已更新。[閱讀全文](../building-journeys/testing-the-journey.md)
* 已更新「測試記錄」章節的外部呼叫錯誤代碼和回應。[閱讀全文](../building-journeys/testing-the-journey.md#viewing_logs)
* 時區管理現已集中在歷程屬性面板中。詳細內容請見[此處](../building-journeys/changing-properties.md#timezone)和[此處](../building-journeys/timezone-management.md)
* 已更新「歷程設計器」章節以反映最近的增強功能。[閱讀全文](../building-journeys/using-the-journey-designer.md)
* 已更新介面說明中內容說明的資訊。[閱讀全文](../about/user-interface.md#section_ksq_zr1_ffb)
* 瀏覽 **XDM 欄位**&#x200B;時現在會顯示好記的名稱。已更新相關章節。[閱讀全文](../about/user-interface.md#friendly-names-display)

## 2020 年 2 月 {#february-2020}

* 已更新捷徑章節。 **C** 鍵盤快速鍵可讓您在所有清單畫面中建立新項目。[閱讀全文](../about/user-interface.md#section_ksq_zr1_ffb)
* [資料來源](../datasource/about-data-sources.md)及[動作](../action/action.md)概述頁面已經過改良。

## 2020 年 1 月 {#january-2020}

* 已在[體驗事件](../datasource/adobe-experience-platform-data-source.md)及[區段](../functions/functioninsegment.md)新增擷取限制。
  <!--* The [getBestSendTime documentation](../functions/functiongetbestsendtime.md) has been updated.-->

## 2019 年 12 月  {#december-2019}

* 已更新所有螢幕擷取畫面以反映介面的變更。
* 已更新測試模式章節。[閱讀全文](../building-journeys/testing-the-journey.md)
  <!--* A warning has been added in the [email send time optimization](../building-journeys/wait-activity.md) and [predictive fatigue scores](../ai-services/leveraging-fatigue-scores.md) sections. These capabilities are only available to customers who use the [Adobe Experience Platform Data Connector](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html).-->
* 現在可刪除已停止的歷程。已更新相關文件頁面。
* 在歷程中偵測到問題時，現在會顯示兩種顏色。紅色代表錯誤，橘色代表警告。[閱讀全文](../about/troubleshooting.md)
* 已更新進階運算式編輯器章節。[閱讀全文](../expression/expressionadvanced.md).
* 已移動和更新[條件式指令](../expression/conditional-instruction.md)和[系列管理](../expression/collection-management-functions.md)章節。
* 已在[函式](../expression/functions.md)章節新增新的範例。
* 已更新 [toDateTime 函式](../functions/functiontodatetime.md)文件以反映時區語法的變更。
