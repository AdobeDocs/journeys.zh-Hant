---
title: 開始使用
description: 開始使用Journey Orchestration
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27

---


# 開始使用{#concept_y4b_4qt_52b}

在「歷程協調」中，有兩種使用者，每一種都執行特定工作：技術使 **用者** ，以及商 **業使用者**。 使用者存取權是透過產品設定檔和權限來管理。 請參閱以 [](../about/access-management.md) 瞭解如何設定使用者存取權。

以下是配置和使用「歷程協調」的主要步驟：

1. **設定事件**

   您需要定義預期的資訊，以及處理方式。 此配置為強制配置。 此步驟由技術使用者 **執行**。

   有關詳細資訊，請參見[](../event/about-events.md)。

   ![](../assets/journey7.png)

1. **設定資料來源**

   您需要定義系統連線，以擷取將用於歷程的其他資訊，例如在您的條件中。 在布建時也會設定內建的Experience platform資料來源。 如果您只運用歷程中事件的資料，則不需要此步驟。 此步驟由技術使用者 **執行**。

   有關詳細資訊，請參見[](../datasource/about-data-sources.md)。

   ![](../assets/journey22.png)

1. **設定動作**

   如果您使用協力廠商系統來傳送訊息，則需使用Journey Orchestration來設定其連線。 參見[](../action/about-custom-action-configuration.md)。

   如果您使用Adobe Campaign standard傳送訊息，則需要設定內建動作。 參見[](../action/working-with-adobe-campaign.md)。

   這些步驟由技術使用 **者執行**。

   ![](../assets/custom2.png)

1. **設計您的旅程**

   結合不同的事件、協調和行動活動，建立您的跨通道多步驟藍本。 此步驟由業務用 **戶執行**。

   有關詳細資訊，請參見 [](../building-journeys/journey.md)。

   ![](../assets/journeyuc2_24.png)

1. **測試並發佈歷程**

   您需要驗證並啟動歷程。 此步驟由業務用 **戶執行**。

   有關詳細資訊，請參見 [](../building-journeys/testing-the-journey.md) 和 [](../building-journeys/publishing-the-journey.md)。

   ![](../assets/journeyuc2_32bis.png)

1. **監控您的歷程**

   使用專屬的報告工具來評估您歷程的成效。 此步驟由業務用 **戶執行**。

   有關詳細資訊，請參見 [](../reporting/about-journey-reports.md)。

   ![](../assets/dynamic_report_journey_12.png)

