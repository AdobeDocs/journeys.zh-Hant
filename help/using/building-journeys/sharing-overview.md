---
product: adobe campaign
solution: Journey Orchestration
title: 歷程步驟分享概觀
description: 歷程步驟分享概觀
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 7%

---


# 歷程步驟分享概觀{#sharing-overview}

[!DNL Journey Orchestration] 自動傳送旅程績效資料至Adobe Experience Platform，以便與其他資料結合以進行分析。

>[!NOTE]
>
>預設情況下，此功能不會在所有新部署的實例上激活。 啟動程式會依要求進行。

例如，您已設定傳送多封電子郵件的歷程。 此功能可讓您將[!DNL Journey Orchestration]資料與下游事件資料結合，例如發生多少轉換、網站上發生多少參與，或在商店中發生多少交易。 旅程資訊可與Adobe Experience Platform的資料結合，不論是來自其他數位屬性或離線屬性，以提供更完整的效能檢視。

[!DNL Journey Orchestration] 自動將個人在旅程中每個步驟的必要結構描述和串流建立至Adobe Experience Platform的資料集。步驟事件對應於在歷程中從一個節點移動到另一個節點的個人。 例如，在具有事件、條件和動作的旅程中，會傳送三個步驟事件至Adobe Experience Platform。

傳遞的XDM欄位清單是完整的。 有些包含系統產生的程式碼，有些則有人類可讀的好記名稱。 範例包括歷程活動的標籤或步驟狀態：動作逾時或錯誤結束的次數。

>[!CAUTION]
>
>無法為即時配置檔案服務開啟資料集。 請確定&#x200B;**[!UICONTROL Profile]**&#x200B;切換已關閉。

歷程會以串流方式在資料發生時傳送資料。 您可以使用查詢服務查詢此資料。 您可以連接到Customer Journey Analytics或其他BI工具來查看與這些步驟相關的資料。

將建立以下結構：

* [!DNL Journey Orchestration]的歷程步驟描述檔事件結構——體驗事件，以瞭解在歷程中所採取的步驟以及用於對應至個別歷程參與者的身分地圖。
* [!DNL Journey Orchestration]的歷程步驟事件結構——系結至歷程中繼資料的歷程步驟事件。
* 使用[!DNL Journey Orchestration]的歷程欄位——歷程中繼資料描述歷程。

![](../assets/sharing1.png)

![](../assets/sharing2.png)

傳遞下列資料集：

* [!DNL Journey Orchestration]的歷程步驟描述檔事件結構
* 歷程步驟活動
* 旅程

![](../assets/sharing3.png)

傳遞給Adobe Experience Platform的XDM欄位清單如下：

* [journeySteps 事件常見欄位](../building-journeys/sharing-common-fields.md)
* [journeyStep 事件動作執行欄位](../building-journeys/sharing-execution-fields.md)
* [journeyStep 事件資料擷取欄位](../building-journeys/sharing-fetch-fields.md)
* [journeyStep 事件識別欄位](../building-journeys/sharing-identity-fields.md)
* [歷程欄位](../building-journeys/sharing-journey-fields.md)

有關向Adobe Experience Platform報告的步驟事件的詳細資訊，請觀看此[教程視頻](https://docs.adobe.com/content/help/en/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html)。
