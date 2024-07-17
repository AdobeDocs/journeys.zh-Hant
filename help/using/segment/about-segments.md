---
product: adobe campaign
title: 關於Adobe Experience Platform區段
description: 瞭解如何設定Adobe Experience Platform區段
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: e5c0db2e1f85ea72fd54f91e4a26cc287377fb0e
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 8%

---

# 關於Adobe Experience Platform區段 {#about-segments}

如果您使用[Adobe Experience Platform Segmentation Service](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=zh-Hant)建立您的區段，可以在[!DNL Journey Orchestration]中運用這些服務。 由於有專屬的活動活動，您可以讓個人根據Adobe Experience Platform區段入口和出口，進入或前進歷程。 這也允許您使用簡單或進階運算式編輯器在歷程中建立複雜條件。

假設您有「銀級客戶」區段。 透過此活動，您可以讓所有新的銀級客戶進入歷程，並向他們傳送一系列個人化訊息。 您也可以根據此區段輕鬆建置條件。

以下是[!DNL Journey Orchestration]提供您區段的可能性：

* 存取Adobe Experience Platform區段的清單。 請參閱[建立區段](../segment/creating-a-segment.md)。
* 直接在[!DNL Journey Orchestration]中建立區段，其方式與使用區段服務建立區段的方式相同。 請參閱[建立區段](../segment/creating-a-segment.md)。
* 使用簡單或進階運算式編輯器，在您的歷程條件中善用區段。 請參閱[在條件](../segment/using-a-segment.md)中使用區段。
* 將&#x200B;**[!UICONTROL Segment qualification]**&#x200B;事件新增至您的歷程，以聆聽Adobe Experience Platform區段中設定檔的入口和出口。 檢視[事件活動](../building-journeys/segment-qualification-events.md)。

## Journey Orchestration中的評估方法 {#evaluation-method-in-journey-orchestration}

在Journey Orchestration中，使用下列其中一種評估方法，從區段定義產生對象：

* 串流區段 — 當新資料流入系統時，區段的對象清單會即時保持最新。
* 批次細分 — 區段的對象清單會根據過去一小時內送達的資料每小時更新。

系統會根據評估區段規則的複雜性和成本，針對每個區段定義來決定批次區段和串流區段之間的差異。

您可以在區段清單的&#x200B;**[!UICONTROL Evaluation method]**&#x200B;欄中檢視每個區段的評估方法。

在您首次定義區段後，設定檔在符合資格時就會新增到受眾。

最多可能需要 24 小時才能從先前的資料回填對象。 回填對象之後，該對象會持續保持在最新狀態，並隨時準備好進行目標定位。