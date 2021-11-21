---
product: adobe campaign
solution: Journey Orchestration
title: 使用 Campaign v7/v8 傳送訊息
description: 使用 Campaign v7/v8 傳送訊息
exl-id: 8832d306-5842-4be5-9fb9-509050fcbb01
source-git-commit: 3e78e429bbdfc95bfef74e0f2e2b92f8ff17cfdb
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 6%

---

# 使用 Campaign v7/v8 傳送訊息 {#campaign-classic-use-case}

此使用案例說明使用Adobe Campaign Classic v7和Adobe Campaign v8整合來傳送電子郵件所需的所有步驟。

我們將先在Campaign中建立交易式電子郵件範本。 接著，在Journey Orchestration中，我們將建立事件、動作並設計歷程。

若要進一步了解Campaign整合，請參閱下列頁面：

* [建立促銷活動動作](../action/acc-action.md)
* [在歷程中使用動作](../building-journeys/using-adobe-campaign-classic.md).

**Adobe Campaign**

您的Campaign執行個體需要布建以進行此整合。 交易式訊息功能需要設定。

1. 登入您的Campaign控制例項。

1. 在 **管理** > **平台** > **列舉**，請選取 **事件類型** (eventType)分項清單。 建立新事件類型（在範例中為「journey-event」）。 您稍後寫入JSON檔案時，必須使用事件類型的內部名稱。

   ![](../assets/accintegration-uc-1.png)

1. 斷開連接並重新連接到實例，以使建立生效。

1. 在 **訊息中心** > **交易式訊息範本**，根據先前建立的事件類型建立新的電子郵件範本。

   ![](../assets/accintegration-uc-2.png)

1. 設計您的範本。 在此範例中，我們會針對設定檔的名字和訂單編號使用個人化。 名字在Adobe Experience Platform資料來源中，訂單號是Journey Orchestration事件中的欄位。 請務必在Campaign中使用正確的欄位名稱。

   ![](../assets/accintegration-uc-3.png)

1. 發佈交易式範本。

   ![](../assets/accintegration-uc-4.png)

1. 現在您需要撰寫與範本對應的JSON裝載。

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

* 針對管道，您需要輸入「電子郵件」。
* 對於eventType，請使用先前建立之事件類型的內部名稱。
* 電子郵件地址會是變數，因此您可以輸入任何標籤。
* 在ctx底下，個人化欄位也是變數。

**Journey Orchestration**

1. 首先，您需要建立事件。 請確定您包含「purchaseOrderNumber」欄位。

   ![](../assets/accintegration-uc-5.png)

1. 然後，您需要以Journey Orchestration建立與促銷活動範本對應的動作。 在 **動作類型** 下拉式清單，選取 **Adobe Campaign Classic**.

   ![](../assets/accintegration-uc-6.png)

1. 按一下 **裝載欄位** 並貼上先前建立的JSON。

   ![](../assets/accintegration-uc-7.png)

1. 對於電子郵件地址和兩個個人化欄位，請變更 **常數** to **變數**.

   ![](../assets/accintegration-uc-8.png)

1. 現在，請建立新的歷程，並從先前建立的事件開始。

   ![](../assets/accintegration-uc-9.png)

1. 新增動作，並將每個欄位對應至Journey Orchestration中的正確欄位。

   ![](../assets/accintegration-uc-10.png)

1. 新增 **結束** 活動並測試您的歷程。

   ![](../assets/accintegration-uc-11.png)

1. 您現在可以發佈歷程。
