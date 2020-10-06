---
title: 開始使用
description: 瞭解設定「歷程協調」的主要步驟，並建立您的第一個歷程。
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 38b555e19b9c3a0757962cbedbf3587e64f69add
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 95%

---


# 開始使用{#concept_y4b_4qt_52b}

[!DNL Journey Orchestration] 中有兩種使用者，每一種都負責執行特定工作，他們分別是&#x200B;**技術使用者**&#x200B;和&#x200B;**業務使用者**。使用者存取權限可透過產品設定檔和權限進行管理。請參閱[](../about/access-management.md)，以瞭解如何設定使用者存取權限。

以下是設定和使用 [!DNL Journey Orchestration] 的主要步驟：

1. **設定事件**

   您需要定義預期的資訊及其處理方式。此設定是強制性的。此步驟由&#x200B;**技術使用者**&#x200B;執行。

   有關詳細資訊，請參閱[](../event/about-events.md)。

   ![](../assets/journey7.png)

1. **設定資料來源**

   您需要定義系統的連線，以擷取將用於歷程的其他資訊，例如在您的條件中。佈建時也會設定內建的 Adobe Experience Platform 資料來源。如果您只會運用歷程中事件的資料，則不需要執行此步驟。此步驟由&#x200B;**技術使用者**&#x200B;執行。

   有關詳細資訊，請參閱[](../datasource/about-data-sources.md)。

   ![](../assets/journey22.png)

1. **設定動作**

   如果您使用協力廠商系統傳送訊息，需要使用 [!DNL Journey Orchestration] 來設定其連線。請參閱[](../action/about-custom-action-configuration.md)。

   如果您使用 Adobe Campaign Standard 傳送訊息，需要設定內建動作。請參閱[](../action/working-with-adobe-campaign.md)。

   這些步驟由&#x200B;**技術使用者**&#x200B;執行。

   ![](../assets/custom2.png)

1. **設計您的歷程**

   結合不同的事件、協調和動作活動，以建立您的多步驟跨管道情境。此步驟由&#x200B;**業務使用者**&#x200B;執行。

   有關詳細資訊，請參閱[](../building-journeys/journey.md)。

   ![](../assets/journeyuc2_24.png)

1. **測試並發佈歷程**

   您需要驗證並啟用歷程。此步驟由&#x200B;**業務使用者**&#x200B;執行。

   有關詳細資訊，請參閱[](../building-journeys/testing-the-journey.md)和[](../building-journeys/publishing-the-journey.md)。

   ![](../assets/journeyuc2_32bis.png)

1. **監視您的歷程**

   使用專屬的報告製作工具來衡量您歷程的成效。此步驟由&#x200B;**業務使用者**&#x200B;執行。

   有關詳細資訊，請參閱[](../reporting/about-journey-reports.md)。

   ![](../assets/dynamic_report_journey_12.png)

