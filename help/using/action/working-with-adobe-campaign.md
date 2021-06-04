---
product: adobe campaign
title: 使用 Adobe Campaign
description: 了解Adobe Campaign動作
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: 04aa7d95c2f12fe03497efe74f2ab8bd1a270b5b
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 2%

---

# 使用 Adobe Campaign {#using_adobe_campaign}

## 使用Adobe Campaign Standard {#using_adobe_campaign_standard}

您可以使用Adobe Campaign Standard的「交易訊息」功能來傳送電子郵件、推播通知和簡訊。

[!DNL Journey Orchestration] 隨附現成可用的動作，可讓您連線至Adobe Campaign Standard。

必須發佈Campaign Standard交易式訊息及其相關事件，才能用於Journey Orchestration。 如果已發佈事件但未顯示訊息，則Journey Orchestration介面中將不會顯示該事件。 如果訊息已發佈，但其相關事件未發佈，則訊息會顯示在Journey Orchestration介面中，但無法使用。

>[!NOTE]
>
>設定Adobe Campaign Standard整合後，系統就會為Adobe Campaign Standard動作自動定義每秒13次呼叫的上限規則。 這對應於Adobe Campaign Standard交易訊息的官方規模。
>
>在[Adobe Campaign Standard產品說明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)中，閱讀更多有關交易式訊息SLA的資訊。

以下是設定此變數的步驟：

1. 從&#x200B;**[!UICONTROL Actions]**&#x200B;清單中，按一下內建&#x200B;**[!UICONTROL AdobeCampaignStandard]**&#x200B;動作。 動作設定窗格會在畫面右側開啟。

   ![](../assets/actioncampaign.png)

1. 複製您的Adobe Campaign Standard執行個體URL並貼到&#x200B;**[!UICONTROL URL]**&#x200B;欄位中。

1. 按一下&#x200B;**[!UICONTROL Test the instance URL]**&#x200B;以測試例項的有效性。

   >[!NOTE]
   >
   >此測試驗證：
   >
   >主機為「.campaign.adobe.com」、「.campaign-sandbox.adobe.com」、「.campaign-demo.adobe.com」、「.ats.adobe.com」或「.adls.adobe.com」。
   >
   >URL的開頭為https,
   >
   >與此Adobe Campaign Standard例項相關聯的組織與Journey Orchestration的組織相同。

設計歷程時，**[!UICONTROL Action]**&#x200B;類別中會提供三個動作：**[!UICONTROL Email]**、**[!UICONTROL Push]**、**[!UICONTROL SMS]**(請參閱[使用Adobe Campaign動作](../building-journeys/using-adobe-campaign-actions.md))。 **反應** 事件也可讓您對訊息點按、開啟等動作做出反應。（請參閱[反應事件](../building-journeys/reaction-events.md)）。

![](../assets/journey58.png)

如果您使用協力廠商系統來傳送訊息，則需要新增及設定自訂動作。 請參閱[關於自訂動作設定](../action/about-custom-action-configuration.md)。

## 使用Adobe Campaign v7/v8 {#using_adobe_campaign_v7_v8}

此整合適用於從21.1版開始的Adobe Campaign Classic v7和Adobe Campaign v8。 它可讓您使用Adobe Campaign交易訊息功能來傳送電子郵件、推播通知和簡訊。

Journey Orchestration與促銷活動例項之間的連線是在布建時Adobe所設定。

此[section](../usecase/campaign-v7-v8-use-case.md)中顯示了端到端使用案例。

對於已設定的每個動作，歷程設計器浮動視窗中都會提供動作活動。 請參閱此[節](../building-journeys/using-adobe-campaign-actions.md)。

### 重要附註

* 消息沒有限制。 根據我們目前的促銷活動SLA，可將可傳送的訊息數量限制為50,000/小時。 因此，Journey Orchestration僅應用於單一使用案例（個別事件，而非區段）。

* 您需要針對要使用的範本，在畫布上設定一個動作。 您需要針對要從Adobe Campaign使用的每個範本，在Journey Orchestration中設定一個動作。

* 建議您使用為此整合托管的專用訊息中心例項，以避免影響您可能進行的任何其他Campaign作業。 行銷伺服器可托管或內部部署。 所需的版本編號為21.1 Release Candiate或更高版本。

* 裝載或促銷活動訊息正確無誤。

* 您無法搭配區段資格事件使用促銷活動動作。

### 先決條件

在Campaign中，您需要建立並發佈交易式訊息及其相關事件。 請參閱[Adobe Campaign檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging)。

您可以依照下列模式，建立與每個訊息對應的JSON裝載。 接著，您會在Journey Orchestration中設定動作時貼上此裝載（請參閱下方）

以下是範例：

```
{
    "channel": "email",
    "eventType": "welcome",
    "email": "example@adobe.com",
    "ctx": {
        "firstName": "John"
    }
}
```

* **管道**:為您的Campaign交易範本定義的管道
* **eventType**:促銷活動事件的內部名稱
* **ctx**:變數。

### 設定動作

在Journey Orchestration中，您需要為每個交易式訊息設定一個動作。 請依照下列步驟操作：

1. 建立新動作。 請參閱此[節](../action/action.md)。
1. 輸入名稱和說明。
1. 在&#x200B;**動作類型**&#x200B;欄位中，選取&#x200B;**Adobe Campaign Classic**。
1. 按一下&#x200B;**裝載**&#x200B;欄位，並貼上與促銷活動訊息對應之JSON裝載的範例。 請聯絡Adobe以取得此裝載。
1. 視您要在歷程畫布上對應不同欄位，將其調整為靜態或變數。 某些欄位(例如電子郵件地址和個人化欄位(ctx)的管道參數)，您可能會想要定義為要在歷程內容中對應的變數。
1. 按一下「**儲存**」。

![](../assets/accintegration1.png)


