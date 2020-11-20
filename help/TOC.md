---
product: adobe campaign
solution: Journey Orchestration
user-guide-title: 歷程協調
title: Journey Orchestration 指南
user-guide-description: 提供實作和構建歷程的操作說明。
index: true
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 99%

---


# [!DNL Journey Orchestration] 指南 {#using}

+ [產品文件](journey-orchestration-home.md)
+ 新增功能 {#release-notes}
   + [發行說明](using/release-notes/release-notes.md)
   + [文件更新](using/release-notes/documentation-updates.md)
+ 開始使用 [!DNL Journey Orchestration] {#starting-with-journeys}
   + [關於 [!DNL Journey Orchestration]](using/about/about-journey-orchestration.md)
   + [限制](using/about/limitations.md)
   + [開始使用](using/about/get-started.md)
   + [使用者介面](using/about/user-interface.md)
   + [存取管理](using/about/access-management.md)
   + [疑難排解](using/about/troubleshooting.md)
+ 設定事件 {#events-journeys}
   + [關於事件](using/event/about-events.md)
   + [關於 ExperienceEvent 結構](using/event/experience-event-schema.md)
   + [定義裝載欄位](using/event/defining-the-payload-fields.md)
   + [選取命名空間](using/event/selecting-the-namespace.md)
   + [定義事件鍵](using/event/defining-the-event-key.md)
   + [新增條件](using/event/adding-a-condition.md)
   + [預覽裝載](using/event/previewing-the-payload.md)
   + [傳送事件的其他步驟](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
+ 設定資料來源 {#data-source-journeys}
   + [關於資料來源](using/datasource/about-data-sources.md)
   + [欄位群組](using/datasource/field-groups.md)
   + [Adobe Experience Platform 資料來源](using/datasource/adobe-experience-platform-data-source.md)
   + [外部資料來源](using/datasource/external-data-sources.md)
+ 設定動作 {#action-journeys}
   + [關於動作](using/action/action.md)
   + [使用 Adobe Campaign](using/action/working-with-adobe-campaign.md)
   + 使用協力廠商系統 {#action-third-party}
      + [關於自訂動作組態](using/action/about-custom-action-configuration.md)
      + [URL 組態](using/action/url-configuration.md)
      + [定義訊息參數](using/action/defining-the-message-parameters.md)
+ 使用 Platform 區段 {#configuring-segment}
   + [關於 Platform 區段](using/segment/about-segments.md)
   + [建立區段](using/segment/creating-a-segment.md)
   + [在條件中使用區段](using/segment/using-a-segment.md)
+ 建立歷程 {#building-journeys}
   + 關於建立歷程 {#about-journey-building}
      + [建立歷程](using/building-journeys/journey.md)
      + [使用歷程設計器](using/building-journeys/using-the-journey-designer.md)
      + [變更屬性](using/building-journeys/changing-properties.md)
      + [歷程版本](using/building-journeys/journey-versions.md)
      + [結束歷程](using/building-journeys/terminating-a-journey.md)
      + [時區管理](using/building-journeys/timezone-management.md)
   + 活動 {#about-journey-building}
      + 事件活動 {#events-activities}
         + [關於事件活動](using/building-journeys/event-activities.md)
         + [一般事件](using/building-journeys/general-events.md)
         + [反應事件](using/building-journeys/reaction-events.md)
         + [區段資格事件](using/building-journeys/segment-qualification-events.md)
      + 協調活動 {#orchestration-activities}
         + [關於協調活動](using/building-journeys/about-orchestration-activities.md)
         + [條件活動](using/building-journeys/condition-activity.md)
         + [結束活動](using/building-journeys/end-activity.md)
         + [等待活動](using/building-journeys/wait-activity.md)
      + 動作活動 {#action-activities}
         + [關於動作活動](using/building-journeys/about-action-activities.md)
         + [使用 Adobe Campaign 動作](using/building-journeys/using-adobe-campaign-actions.md)
         + [使用自訂動作](using/building-journeys/using-custom-actions.md)
   + [測試歷程](using/building-journeys/testing-the-journey.md)
   + [發佈歷程](using/building-journeys/publishing-the-journey.md)
   + 使用 Adobe Experience Platform 分享歷程步驟 {#sharing-journey-steps}
      + [歷程步驟分享概觀](using/building-journeys/sharing-overview.md)
      + [journeySteps 事件常見欄位](using/building-journeys/sharing-common-fields.md)
      + [journeyStep 事件動作執行欄位](using/building-journeys/sharing-execution-fields.md)
      + [journeyStep 事件資料擷取欄位](using/building-journeys/sharing-fetch-fields.md)
      + [journeyStep 事件識別欄位](using/building-journeys/sharing-identity-fields.md)
      + [歷程欄位](using/building-journeys/sharing-journey-fields.md)
+ 使用進階運算式編輯器 {#building-advanced-conditions-journeys}
   + [關於進階運算式編輯器](using/expression/expressionadvanced.md)
   + 語法 {#syntax}
      + [一般性](using/expression/generalities.md)
      + [條件式指令](using/expression/conditional-instruction.md)
      + [資料類型](using/expression/data-types.md)
      + [欄位參考](using/expression/field-references.md)
      + [收集管理函式](using/expression/collection-management-functions.md)
      + [運算子](using/expression/operators.md)
      + [範例](using/expression/advanced-editor-use-cases.md)
   + 函式 {#main-functions-journey}
      + [主要函式](using/expression/functions.md)
      + Adobe Experience Platform {#adobe-experience-platform}
         + [inSegment](using/functions/functioninsegment.md)
      + 彙總 {#aggregation}
         + [avg](using/functions/functionavg.md)
         + [count](using/functions/functioncount.md)
         + [countOnlyNull](using/functions/functioncountonlynull.md)
         + [countWithNull](using/functions/functioncountwithnull.md)
         + [distinctCount](using/functions/functiondistinctcount.md)
         + [distinctCountWithNull](using/functions/functiondistinctcountwithnull.md)
         + [max](using/functions/functionmax.md)
         + [min](using/functions/functionmin.md)
         + [sum](using/functions/functionsum.md)
      + 轉換 {#conversion}
         + [toBool](using/functions/functiontobool.md)
         + [toDateTime](using/functions/functiontodatetime.md)
         + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
         + [toDecimal](using/functions/functiontodecimal.md)
         + [toDuration](using/functions/functiontoduration.md)
         + [toInteger](using/functions/functiontointeger.md)
         + [toString](using/functions/functiontostring.md)
      + 日期 {#date}
         + [currentTime&#x200B;InMillis](using/functions/functioncurrenttimeinmillis.md)
         + [inLastDays](using/functions/functioninlastdays.md)
         + [inLastHours](using/functions/functioninlasthours.md)
         + [inLastMonths](using/functions/functioninlastmonths.md)
         + [inLastYears](using/functions/functioninlastyears.md)
         + [inNextDays](using/functions/functioninnextdays.md)
         + [inNextHours](using/functions/functioninnexthours.md)
         + [inNextMonths](using/functions/functioninnextmonths.md)
         + [inNextYears](using/functions/functioninnextyears.md)
         + [now](using/functions/functionnow.md)
         + [nowWithDelta](using/functions/functionnowwithdelta.md)
         + [setHours](using/functions/functionsethours.md)
         + [setDays](using/functions/functionsetdays.md)
      + 清單 {#list}
         + [distict](using/functions/functiondistinct.md)
         + [distinctWithNull](using/functions/functiondistinctwithnull.md)
         + [in](using/functions/functionin.md)
         + [listSize](using/functions/functionlistsize.md)
         + [serializeList](using/functions/functionserializelist.md)
         + [sort](using/functions/functionsort.md)
      + 數學 {#math}
         + [random](using/functions/functionrandom.md)
         + [round](using/functions/functionround.md)
      + 字串 {#string}
         + [concat](using/functions/functionconcat.md)
         + [contain](using/functions/functioncontain.md)
         + [containWithIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
         + [equalWithIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [isEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [length](using/functions/functionlength.md)
         + [lower](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notEqualWithIgnoreCase](using/functions/functionnotequalignorecase.md)
         + [replace](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [substr](using/functions/functionsubstr.md)
         + [trim](using/functions/functiontrim.md)
         + [upper](using/functions/functionupper.md)
         + [uid](using/functions/functionuuid.md)
+ 建立報表{#journey-reports}
   + [關於歷程報告](using/reporting/about-journey-reports.md)
   + [建立您的歷程報告](using/reporting/creating-your-journey-reports.md)
   + [量度與維度](using/reporting/metrics-and-dimensions.md)
+ 與智慧型服務整合{#use-case-advanced}
   + [關於 AI 整合](using/ai-services/ai-services-overview.md)
   + [善用客戶 AI](using/ai-services/leveraging-customer-ai.md)
+ 使用案例{#use-cases-journeys}
   + 傳送個人化電子郵件{#use-case-simple}
      + [關於簡單使用案例](using/usecase/about-the-simple-use-case.md)
      + [設定事件](using/usecase/configuring-the-event.md)
      + [設定資料來源](using/usecase/configuring-the-data-source.md)
      + [建立歷程](using/usecase/simple-uc-building-the-journey.md)
   + 構建跨管道之旅。{#use-case-advanced}
      + [關於進階使用案例](using/usecase/about-the-advanced-use-case.md)
      + [設定事件](using/usecase/configuring-the-events.md)
      + [設定資料來源](using/usecase/configuring-the-data-sources.md)
      + [建立歷程](using/usecase/building-the-journey.md)
+ 使用 API{#working-with-apis}
   + [設定 API 上限](using/api/capping.md)
+ Alpha 功能 {#alpha}
   + [Alpha 功能概觀](using/alpha/alpha-overview.md)
   + [使用者介面](using/alpha/alpha-interface.md)
   + [閱讀區段活動](using/alpha/alpha-segment-trigger.md)
   + [規則型事件](using/alpha/alpha-events.md)

