---
product: adobe campaign
solution: Journey Orchestration
title: 使用 Campaign v7/v8 傳送訊息
description: 使用 Campaign v7/v8 傳送訊息
source-git-commit: 2195ee3863b38ead504eb6785ceb3c37735fade9
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 6%

---

# 使用 Campaign v7/v8 傳送訊息 {#campaign-classic-use-case}

此使用情形顯示了使用與Adobe Campaign Classicv7和Adobe Campaignv8的整合發送電子郵件所需的所有步驟。

我們將首先在市場活動中建立事務性電子郵件模板。 然後，在Journey Orchestration中，我們將建立活動、行動和設計旅程。

要瞭解有關市場活動整合的詳細資訊，請參閱以下頁：

* [建立市場活動活動](../action/acc-action.md)
* [在旅途中使用動作](../building-journeys/using-adobe-campaign-classic.md)。

**Adobe Campaign**

需要為此整合預配您的市場活動實例。 需要配置事務性消息傳遞功能。

1. 登錄到您的市場活動控制實例。

1. 下 **管理** > **平台** > **枚舉**，選擇 **事件類型** (eventType)枚舉。 建立新事件類型（在示例中為「journey-event」）。 以後寫入JSON檔案時，必須使用事件類型的內部名稱。

   ![](../assets/accintegration-uc-1.png)

1. 斷開連接並重新連接到實例，以使建立生效。

1. 下 **消息中心** > **事務性消息模板**，根據先前建立的事件類型建立新電子郵件模板。

   ![](../assets/accintegration-uc-2.png)

1. 設計模板。 在本示例中，我們對配置檔案的名字和訂單號使用個性化。 名字在Adobe Experience Platform資料源中，訂單號是我們的Journey Orchestration事件中的欄位。 確保在「市場活動」中使用正確的欄位名稱。

   ![](../assets/accintegration-uc-3.png)

1. 發佈事務模板。

   ![](../assets/accintegration-uc-4.png)

1. 現在，您需要編寫與模板對應的JSON負載。

```
{
     "channel": "email",
     "eventType": "journey-event",
     "email": "Email address",
     "ctx": {
          "firstName": "First name", "purchaseOrderNumber": "Purchase order number"
     }
}
```

* 對於頻道，您需要鍵入「email」。
* 對於eventType，使用先前建立的事件類型的內部名稱。
* 電子郵件地址將是變數，因此您可以鍵入任何標籤。
* 在ctx下，個性化欄位也是變數。

**Journey Orchestration**

1. 首先，您需要建立一個事件。 確保包括「purchaseOrderNumber」欄位。

   ![](../assets/accintegration-uc-5.png)

1. 然後，您需要以Journey Orchestration方式建立與市場活動模板對應的活動。 在 **操作類型** 下拉，選擇 **Adobe Campaign Classic**。

   ![](../assets/accintegration-uc-6.png)

1. 按一下 **負載欄位** 並貼上以前建立的JSON。

   ![](../assets/accintegration-uc-7.png)

1. 對於電子郵件地址和兩個個性化欄位，請更改 **常數** 至 **變數**。

   ![](../assets/accintegration-uc-8.png)

1. 現在建立新行程，並從先前建立的事件開始。

   ![](../assets/accintegration-uc-9.png)

1. 添加操作，並將每個欄位映射到Journey Orchestration中的正確欄位。

   ![](../assets/accintegration-uc-10.png)

1. 添加 **結束** 活動，test旅程。

   ![](../assets/accintegration-uc-11.png)

1. 你現在可以發表你的旅程。
