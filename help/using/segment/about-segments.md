---
product: adobe campaign
title: 關於Adobe Experience Platform區段
description: 了解如何設定Adobe Experience Platform區段
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: e5c0db2e1f85ea72fd54f91e4a26cc287377fb0e
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 0%

---

# 關於Adobe Experience Platform區段 {#about-segments}

如果您使用[Adobe Experience Platform分段服務](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html)來建立區段，您可以在[!DNL Journey Orchestration]中運用這些區段。 有了專屬的活動活動，您可以根據Adobe Experience Platform區段入口和出口，讓個人進入歷程或前進。 這也可讓您使用簡單或進階運算式編輯器，在歷程中建立複雜條件。

假設您有「銀色客戶」區段。 透過此活動，您可以讓所有新銀級客戶進入歷程，並傳送一系列個人化訊息。 您也可以輕鬆根據此區段建立條件。

以下是具有區段的可能性[!DNL Journey Orchestration]:

* 存取Adobe Experience Platform區段清單。 請參閱[建立區段](../segment/creating-a-segment.md)。
* 直接在[!DNL Journey Orchestration]中建立區段，方式與使用區段服務建立區段的方式相同。 請參閱[建立區段](../segment/creating-a-segment.md)。
* 使用簡單或進階運算式編輯器，在歷程的條件中運用區段。 請參閱在條件](../segment/using-a-segment.md)中使用區段。[
* 新增&#x200B;**[!UICONTROL Segment qualification]**&#x200B;事件至您的歷程，以監聽Adobe Experience Platform區段中設定檔的入口和出口。 請參閱[事件活動](../building-journeys/segment-qualification-events.md)。

## Journey Orchestration中的評價方法 {#evaluation-method-in-journey-orchestration}

在Journey Orchestration中，觀眾是使用下列其中一種評估方法從區段定義產生：

* 串流區段 — 當新資料流入系統時，區段的對象清單會即時保持最新。
* 批次區段 — 區段的對象清單會根據過去一小時內到達的資料，每小時更新一次。

系統會根據評估區段規則的複雜度和成本，對每個區段定義進行批次分段和串流分段之間的決定。

您可以在區段清單的&#x200B;**[!UICONTROL Evaluation method]**&#x200B;欄中檢視每個區段的評估方法。

在您首次定義區段後，設定檔會在符合資格時新增至對象。

從先前的資料回填受眾最多需要24小時。 回填對象後，對象會持續保持最新狀態，且隨時準備進行目標定位。