---
product: adobe campaign
solution: Journey Orchestration
title: 使用 Campaign v7/v8 傳送訊息
description: 使用 Campaign v7/v8 傳送訊息
exl-id: 717a927a-4357-4058-a626-1b69f4bb46bc
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 5%

---

# 使用 Campaign v7/v8 傳送訊息 {#campaign-classic-use-case}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_


此使用案例會介紹使用與Adobe Campaign Classic v7和Adobe Campaign v8的整合來傳送電子郵件所需的所有步驟。

我們將先在Campaign中建立交易式電子郵件範本。 然後，在Journey Orchestration中，我們將建立事件、動作並設計歷程。

若要瞭解有關Campaign整合的詳細資訊，請參閱以下頁面：

* [建立行銷活動動作](../action/acc-action.md)
* [在歷程中使用動作](../building-journeys/using-adobe-campaign-classic.md)。

**Adobe Campaign**

需要布建您的Campaign執行個體才能進行此整合。 需要設定異動訊息傳送功能。

1. 登入您的Campaign控制例項。

1. 在&#x200B;**管理** > **平台** > **列舉**&#x200B;下，選取&#x200B;**事件型別** (eventType)列舉。 建立新的事件型別（範例中為「journey-event」）。 稍後寫入JSON檔案時，您必須使用事件型別的內部名稱。

   ![](../assets/accintegration-uc-1.png)

1. 中斷連線並重新連線到執行個體，以便建立生效。

1. 在&#x200B;**訊息中心** > **異動訊息範本**&#x200B;下，根據先前建立的事件型別建立新的電子郵件範本。

   ![](../assets/accintegration-uc-2.png)

1. 設計您的範本。 在此範例中，我們會對設定檔的名字和訂單編號使用個人化。 名字位於Adobe Experience Platform資料來源中，而訂單編號則是來自Journey Orchestration事件的欄位。 請務必在Campaign中使用正確的欄位名稱。

   ![](../assets/accintegration-uc-3.png)

1. 發佈您的交易式範本。

   ![](../assets/accintegration-uc-4.png)

1. 現在您需要撰寫與範本相對應的JSON裝載。

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

* 對於頻道，您需要輸入「電子郵件」。
* 對於eventType，請使用先前建立之事件型別的內部名稱。
* 電子郵件地址將是變數，因此您可以鍵入任何標籤。
* 在ctx底下，個人化欄位也是變數。

**Journey Orchestration**

1. 首先，您必須建立事件。 請務必加入「purchaseOrderNumber」欄位。

   ![](../assets/accintegration-uc-5.png)

1. 然後，您需要在Journey Orchestration中建立與行銷活動範本對應的動作。 在&#x200B;**動作型別**&#x200B;下拉式清單中，選取&#x200B;**Adobe Campaign Classic**。

   ![](../assets/accintegration-uc-6.png)

1. 按一下&#x200B;**裝載欄位**&#x200B;並貼上先前建立的JSON。

   ![](../assets/accintegration-uc-7.png)

1. 針對電子郵件地址和兩個個人化欄位，將&#x200B;**常數**&#x200B;變更為&#x200B;**變數**。

   ![](../assets/accintegration-uc-8.png)

1. 現在建立新歷程，並從先前建立的事件開始。

   ![](../assets/accintegration-uc-9.png)

1. 新增動作，並將每個欄位對應至Journey Orchestration中的正確欄位。

   ![](../assets/accintegration-uc-10.png)

1. 新增&#x200B;**結束**&#x200B;活動並測試您的歷程。

   ![](../assets/accintegration-uc-11.png)

1. 您現在可以發佈您的歷程。
