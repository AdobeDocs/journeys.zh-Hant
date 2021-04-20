---
product: adobe campaign
solution: Journey Orchestration
title: 使用 Adobe Campaign
description: 瞭解Adobe Campaign行動
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 8685dfdcbfb414af89b304a6a9a0f9418959909b
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 4%

---


# 使用 Adobe Campaign {#using_adobe_campaign_standard}

您可以使用Adobe Campaign Standard的交易訊息功能來傳送電子郵件、推播通知和簡訊。

[!DNL Journey Orchestration] 隨附現成可用的動作，讓您與Adobe Campaign Standard的連線。

Campaign Standard事務性消息及其關聯事件必須發佈，才能用於Journey Orchestration。 如果事件已發佈，但訊息未發佈，則不會顯示在Journey Orchestration介面中。 如果訊息已發佈，但其關聯事件未發佈，則訊息會顯示在Journey Orchestration介面中，但無法使用。

>[!NOTE]
>
>一旦設定了Adobe Campaign Standard整合，就會自動為Adobe Campaign Standard動作定義每秒13個呼叫的上限規則。 這與Adobe Campaign Standard交易訊息的官方規模相符。
>
>閱讀[Adobe Campaign Standard產品說明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)中有關事務性消息傳遞SLA的更多資訊。

以下是設定它的步驟：

1. 從&#x200B;**[!UICONTROL Actions]**&#x200B;清單中，按一下內建&#x200B;**[!UICONTROL AdobeCampaignStandard]**&#x200B;動作。 動作設定窗格會在畫面的右側開啟。

   ![](../assets/actioncampaign.png)

1. 複製您的Adobe Campaign Standard實例URL並將其貼上到&#x200B;**[!UICONTROL URL]**&#x200B;欄位中。

1. 按一下&#x200B;**[!UICONTROL Test the instance URL]**&#x200B;以測試例項的有效性。

   >[!NOTE]
   >
   >此測試可驗證：
   >
   >主機為&quot;。campaign.adobe.com&quot;、&quot;。campaign-sandbox.adobe.com&quot;、&quot;。campaign-demo.adobe.com&quot;、&quot;。ats.adobe.com&quot;或&quot;。adls.adobe.com&quot;。
   >
   >URL以https開頭，
   >
   >與此Adobe Campaign Standard實例關聯的ORG與Journey Orchestration的ORG相同。

在設計您的歷程時，**[!UICONTROL Action]**&#x200B;類別中會提供三個動作：**[!UICONTROL Email]**、**[!UICONTROL Push]**、**[!UICONTROL SMS]**(請參閱[使用Adobe Campaign操作](../building-journeys/using-adobe-campaign-actions.md))。 **反應** 甚至可讓您對訊息點按、開啟等做出反應。（請參閱[Reactions events](../building-journeys/reaction-events.md)）。

![](../assets/journey58.png)

如果您使用協力廠商系統來傳送訊息，則需要新增及設定自訂動作。 請參閱[關於自訂動作設定](../action/about-custom-action-configuration.md)。
