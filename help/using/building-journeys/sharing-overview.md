---
product: adobe campaign
title: 歷程步驟分享概覽
description: 歷程步驟分享概覽
feature: Journeys
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: bb07c0edaae469962ee3bf678664b4a0a83572fe
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 3%

---

# 歷程步驟分享概覽{#sharing-overview}

[!DNL Journey Orchestration]會自動將歷程績效資料傳送至Adobe Experience Platform，以便與其他資料結合而進行分析。

>[!NOTE]
>
>此功能預設會在歷程步驟事件的所有執行個體上啟動。 您無法修改或更新在布建步驟事件期間建立的結構描述和資料集。 預設情況下，這些結構描述和資料集處於唯讀模式。

例如，您已設定傳送多封電子郵件的歷程。 此功能可讓您將[!DNL Journey Orchestration]資料與下游事件資料結合，例如發生轉換數、網站上發生的參與數，或商店中發生的交易數。 歷程資訊可以與Adobe Experience Platform上的資料結合，來自其他數位屬性或離線屬性，以提供更完整的效能檢視。

[!DNL Journey Orchestration]會自動建立必要的結構描述，並針對個人在歷程中採取的每個步驟，將資料集串流至Adobe Experience Platform。 步驟事件對應於在歷程中從某個節點移動到另一個節點的個人。 例如，在包含事件、條件和動作的歷程中，會將三個步驟事件傳送至Adobe Experience Platform。

傳遞的XDM欄位清單是完整的。 有些包含系統產生的程式碼，有些則有人類看得懂的易記名稱。 範例包括歷程活動的標籤或步驟狀態：動作逾時或錯誤結束的次數。

>[!CAUTION]
>
>無法為即時設定檔服務開啟資料集。 請確定已關閉&#x200B;**[!UICONTROL Profile]**&#x200B;切換。

歷程會在資料發生時以串流方式傳送資料。 您可以使用查詢服務來查詢此資料。 您可以連線至Customer Journey Analytics或其他BI工具，以檢視與這些步驟相關的資料。

將建立下列結構描述：

* [!DNL Journey Orchestration]的歷程步驟事件結構描述 — 繫結至歷程中繼資料的歷程步驟事件。
* 具有[!DNL Journey Orchestration]的歷程欄位的歷程結構描述 — 描述歷程的歷程中繼資料。

![](../assets/sharing1.png)

![](../assets/sharing2.png)

會傳遞下列資料集：

* 歷程步驟事件
* 歷程

![](../assets/sharing3.png)

傳遞至Adobe Experience Platform的XDM欄位清單詳細說明：

* [步驟事件欄位清單](../building-journeys/sharing-field-list.md)
* [舊版步驟事件欄位](../building-journeys/sharing-legacy-fields.md)

如需向Adobe Experience Platform報告之步驟事件的詳細資訊，請觀看此[教學課程影片](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html)。

## 與Customer Journey Analytics整合{#integration-cja}

Journey Orchestration步驟事件可以連結到[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hant)中的其他資料集。 以下是一般工作流程：

* Customer Journey Analytics會擷取「歷程步驟事件」資料集。
* 關聯的「用於Journey Orchestration的歷程步驟事件結構描述」中的&#x200B;**profileID**&#x200B;欄位定義為身分欄位。 在Customer Journey Analytics中，您可以將此資料集連結至與以人員為基礎的識別碼具有相同值的任何其他資料集。
* 如果您想要在Customer Journey Analytics中使用此資料集，如需進行跨管道歷程分析，請參閱此[檔案](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/cross-channel.html)。
