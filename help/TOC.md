---
product: Journeys
audience: end-user
user-guide-title: Journey Orchestration Help
index: true
translation-type: tm+mt
source-git-commit: 22569d66acb1637efc346f77864302b9e2cb6070

---


# 歷程協調說明 {#using}

+ [產品文檔](journey-orchestration-home.md)
+ What&#39;s new {#release-notes}
   + [發行說明](using/release-notes/release-notes.md)
   + [文檔更新](using/release-notes/documentation-updates.md)
+ 從歷程協調開始 {#starting-with-journeys}
   + [關於歷程協調](using/about/about-journey-orchestration.md)
   + [開始使用](using/about/get-started.md)
   + [使用者介面](using/about/user-interface.md)
   + [存取管理](using/about/access-management.md)
   + [疑難排解](using/about/troubleshooting.md)
+ 設定事件 {#events-journeys}
   + [關於事件](using/event/about-events.md)
   + [定義裝載欄位](using/event/defining-the-payload-fields.md)
   + [選擇命名空間](using/event/selecting-the-namespace.md)
   + [定義事件鍵](using/event/defining-the-event-key.md)
   + [新增條件](using/event/adding-a-condition.md)
   + [預覽裝載](using/event/previewing-the-payload.md)
   + [傳送事件的其他步驟](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
+ 配置資料源 {#data-source-journeys}
   + [關於資料來源](using/datasource/about-data-sources.md)
   + [欄位群組](using/datasource/field-groups.md)
   + [Adobe Experience platform資料來源](using/datasource/adobe-experience-platform-data-source.md)
   + [外部資料來源](using/datasource/external-data-sources.md)
+ 設定動作 {#action-journeys}
   + [關於動作](using/action/action.md)
   + [使用Adobe Campaign](using/action/working-with-adobe-campaign.md)
   + 使用協力廠商系統 {#action-third-party}
      + [關於自訂動作設定](using/action/about-custom-action-configuration.md)
      + [自訂動作限制](using/action/custom-action-limitations.md)
      + [URL設定](using/action/url-configuration.md)
      + [定義消息參數](using/action/defining-the-message-parameters.md)
+ 建立歷程 {#building-journeys}
   + 關於歷程建置 {#about-journey-building}
      + [建立歷程](using/building-journeys/journey.md)
      + [使用歷程設計人員](using/building-journeys/using-the-journey-designer.md)
      + [變更屬性](using/building-journeys/changing-properties.md)
      + [歷程版本](using/building-journeys/journey-versions.md)
      + [結束歷程](using/building-journeys/terminating-a-journey.md)
      + [時區管理](using/building-journeys/timezone-management.md)
   + 活動 {#about-journey-building}
      + [活動活動](using/building-journeys/event-activities.md)
      + 協調活動 {#orchestration-activities}
         + [關於協調活動](using/building-journeys/about-orchestration-activities.md)
         + [條件活動](using/building-journeys/condition-activity.md)
         + [結束活動](using/building-journeys/end-activity.md)
         + [等待活動](using/building-journeys/wait-activity.md)
      + 行動活動 {#action-activities}
         + [關於動作活動](using/building-journeys/about-action-activities.md)
         + [使用Adobe Campaign動作](using/building-journeys/using-adobe-campaign-actions.md)
         + [使用自訂動作](using/building-journeys/using-custom-actions.md)
   + [測試旅程](using/building-journeys/testing-the-journey.md)
   + [發佈歷程](using/building-journeys/publishing-the-journey.md)
+ 使用進階運算式編輯器 {#building-advanced-conditions-journeys}
   + [關於進階運算式編輯器](using/expression/expressionadvanced.md)
   + 語法 {#syntax}
      + [一般性](using/expression/generalities.md)
      + [條件式指令](using/expression/conditional-instruction.md)
      + [資料類型](using/expression/data-types.md)
      + [欄位參考](using/expression/field-references.md)
      + [收集管理功能](using/expression/collection-management-functions.md)
      + [營運商](using/expression/operators.md)
   + 函式 {#main-functions-journey}
      + [主要功能](using/expression/functions.md)
      + Adobe Experience Platform {#adobe-experience-platform}
         + [getBestSendTime](using/functions/functiongetbestsendtime.md)
         + [inSegment](using/functions/functioninsegment.md)
      + 聚合 {#aggregation}
         + [平均](using/functions/functionavg.md)
         + [計數](using/functions/functioncount.md)
         + [countOnlyNull](using/functions/functioncountonlynull.md)
         + [countWithNull](using/functions/functioncountwithnull.md)
         + [distinctCount](using/functions/functiondistinctcount.md)
         + [distinctCountWithNull](using/functions/functiondistinctcountwithnull.md)
         + [max](using/functions/functionmax.md)
         + [min](using/functions/functionmin.md)
         + [總和](using/functions/functionsum.md)
      + 轉換 {#conversion}
         + [toBool](using/functions/functiontobool.md)
         + [toDateTime](using/functions/functiontodatetime.md)
         + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
         + [toDecimal](using/functions/functiontodecimal.md)
         + [toDuration](using/functions/functiontoduration.md)
         + [toInteger](using/functions/functiontointeger.md)
         + [toString](using/functions/functiontostring.md)
      + 日期 {#date}
         + [currentTime &#x200B; InMillis](using/functions/functioncurrenttimeinmillis.md)
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
         + [序列化清單](using/functions/functionserializelist.md)
         + [排序](using/functions/functionsort.md)
      + 數學 {#math}
         + [隨機](using/functions/functionrandom.md)
         + [圓](using/functions/functionround.md)
      + 字串 {#string}
         + [康卡特](using/functions/functionconcat.md)
         + [contain](using/functions/functioncontain.md)
         + [containWithIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
         + [equalWithIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [isEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [長度](using/functions/functionlength.md)
         + [lower](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notEqualWithIgnoreCase](using/functions/functionnotequalignorecase.md)
         + [替換](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [substr](using/functions/functionsubstr.md)
         + [修剪](using/functions/functiontrim.md)
         + [上](using/functions/functionupper.md)
         + [uid](using/functions/functionuuid.md)
+ 建立報表{#journey-reports}
   + [關於歷程報告](using/reporting/about-journey-reports.md)
   + [建立您的歷程報表](using/reporting/creating-your-journey-reports.md)
   + [量度與維度](using/reporting/metrics-and-dimensions.md)
+ 使用案例{#use-cases-journeys}
   + 簡單使用案例{#use-case-simple}
      + [關於簡單使用案例](using/usecase/about-the-simple-use-case.md)
      + [設定事件](using/usecase/configuring-the-event.md)
      + [配置資料源](using/usecase/configuring-the-data-source.md)
      + [打造旅程](using/usecase/simple-uc-building-the-journey.md)
   + 進階使用案例{#use-case-advanced}
      + [關於進階使用案例](using/usecase/about-the-advanced-use-case.md)
      + [設定事件](using/usecase/configuring-the-events.md)
      + [設定資料來源](using/usecase/configuring-the-data-sources.md)
      + [打造旅程](using/usecase/building-the-journey.md)
   + [運用疲勞分數](using/usecase/leveraging-fatigue-scores.md)

