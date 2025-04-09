---
product: adobe campaign
title: 開始使用
description: 探索設定 Journey Orchestration 的主要步驟，並建置您的第一個歷程。
feature: Journeys
role: User
level: Beginner
exl-id: fe7bb5fe-7b5e-46da-8ef8-ae9401522c03
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 88%

---

# 開始使用{#concept_y4b_4qt_52b}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_




[!DNL Journey Orchestration] 中有兩種使用者，每一種都負責執行特定工作，他們分別是&#x200B;**技術使用者**&#x200B;和&#x200B;**業務使用者**。可透過產品設定檔和權限管理使用者權限。請參閱[此頁面](../about/access-management.md)，以瞭解如何設定使用者存取權限。

以下是設定和使用 [!DNL Journey Orchestration] 的主要步驟：

1. **設定事件**

   您需要定義預期的資訊及其處理方式。此設定是強制性的。此步驟由&#x200B;**技術使用者**&#x200B;執行。

   如需詳細資訊，請參閱[此頁面](../event/about-events.md)。

   ![](../assets/journey7.png)

1. **設定資料來源**

   您需要定義系統的連線，以擷取將用於歷程的其他資訊，例如在您的條件中。佈建時也會設定內建的 Adobe Experience Platform 資料來源。如果您只會運用歷程中事件的資料，則不需要執行此步驟。此步驟由&#x200B;**技術使用者**&#x200B;執行。

   如需詳細資訊，請參閱[此頁面](../datasource/about-data-sources.md)。

   ![](../assets/journey22.png)

1. **設定動作**

   如果您使用協力廠商系統傳送訊息，需要使用 [!DNL Journey Orchestration] 來設定其連線。請參閱[此頁面](../action/about-custom-action-configuration.md)。

   如果您要使用 Adobe Campaign Standard 傳送訊息，需要設定內建動作。請參閱[此頁面](../action/working-with-adobe-campaign.md)。

   這些步驟由&#x200B;**技術使用者**&#x200B;執行。

   ![](../assets/custom2.png)

1. **設計您的歷程**

   結合不同的事件、協調和動作活動，以建立您的多步驟跨管道情境。此步驟由&#x200B;**業務使用者**&#x200B;執行。

   如需詳細資訊，請參閱[此頁面](../building-journeys/journey.md)。

   ![](../assets/journeyuc2_24.png)

1. **測試並發佈歷程**

   您需要驗證並啟用歷程。此步驟由&#x200B;**業務使用者**&#x200B;執行。

   如需詳細資訊，請參閱[測試歷程](../building-journeys/testing-the-journey.md)和[發佈歷程](../building-journeys/publishing-the-journey.md)頁面。

   ![](../assets/journeyuc2_32bis.png)

1. **監視您的歷程**

   使用專屬的報告製作工具來衡量您歷程的成效。此步驟由&#x200B;**業務使用者**&#x200B;執行。

   如需詳細資訊，請參閱[此頁面](../reporting/about-journey-reports.md)。

   ![](../assets/dynamic_report_journey_12.png)
