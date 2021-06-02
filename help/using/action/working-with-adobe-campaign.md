---
product: adobe campaign
title: 使用 Adobe Campaign
description: 了解Adobe Campaign動作
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 4%

---

# 使用 Adobe Campaign {#using_adobe_campaign_standard}

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
