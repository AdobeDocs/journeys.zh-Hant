---
product: adobe campaign
title: 歷程步驟分享概覽
description: 歷程步驟分享概覽
feature: Journeys
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: b557e94076bc7ce5c212246ddf313248ca10dd60
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 2%

---

# 歷程步驟分享概覽{#sharing-overview}

[!DNL Journey Orchestration] 自動將歷程績效資料傳送至Adobe Experience Platform，以便與其他資料結合以進行分析。

>[!NOTE]
>
>此功能預設會在歷程步驟事件的所有執行個體上啟用。 若為歷程設定檔步驟事件，則需應要求進行啟動。 您無法修改或更新在布建步驟事件期間建立的結構和資料集。 這些結構和資料集預設為唯讀模式。

例如，您已設定可傳送多封電子郵件的歷程。 此功能可讓您結合 [!DNL Journey Orchestration] 具有下游事件資料的資料，例如發生了多少次轉換、網站上發生了多少參與，或商店中發生了多少交易。 歷程資訊可與Adobe Experience Platform上的資料結合，不論是來自其他數位屬性或來自離線屬性，以提供更全面的效能檢視。

[!DNL Journey Orchestration] 針對個人在歷程中執行的每個步驟，自動將必要的結構描述和資料流建立至Adobe Experience Platform。 步驟事件對應至歷程中從一個節點移至另一個節點的個人。 例如，在具有事件、條件和動作的歷程中，會將三個步驟事件傳送至Adobe Experience Platform。

傳遞的XDM欄位清單為完整。 有些包含系統產生的程式碼，有些則有人類看得懂的易記名稱。 範例包括歷程活動的標籤或步驟狀態：動作逾時或因錯誤而結束的次數。

>[!CAUTION]
>
>無法為即時設定檔服務開啟資料集。 請確定 **[!UICONTROL Profile]** 切換為關閉。

歷程會以串流方式在資料發生時傳送。 您可以使用查詢服務查詢此資料。 您可以連線至Customer Journey Analytics或其他BI工具，以檢視與這些步驟相關的資料。

會建立下列結構：

* 適用於的歷程步驟描述檔事件結構 [!DNL Journey Orchestration]  — 體驗事件，以了解在歷程中所採取的步驟，以及用於對應至個別歷程參與者的身分對應。
* 適用於的歷程步驟事件結構 [!DNL Journey Orchestration]  — 系結至歷程中繼資料的歷程步驟事件。
* 具有歷程欄位的歷程結構 [!DNL Journey Orchestration]  — 描述歷程的歷程中繼資料。

![](../assets/sharing1.png)

![](../assets/sharing2.png)

會傳遞下列資料集：

* 適用於的歷程步驟描述檔事件結構 [!DNL Journey Orchestration]
* 歷程步驟事件
* 歷程

![](../assets/sharing3.png)

傳遞至Adobe Experience Platform的XDM欄位清單詳列於此處：

* [步驟事件欄位清單](../building-journeys/sharing-field-list.md)
* [舊版步驟事件欄位](../building-journeys/sharing-legacy-fields.md)

如需向Adobe Experience Platform報告步驟事件的詳細資訊，請觀看此影片 [教學課程影片](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html).
