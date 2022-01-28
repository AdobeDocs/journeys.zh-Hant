---
product: adobe campaign
title: 使用 Adobe Campaign
description: 瞭解Adobe Campaign操作
feature: Journeys
role: User
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: 545352efdcda80cb9940010c4587a20f53326085
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 4%

---

# 使用 Adobe Campaign Standard {#using_adobe_campaign_standard}

您可以使用Adobe Campaign Standard的事務性消息傳遞功能發送電子郵件、推送通知和SMS。

[!DNL Journey Orchestration] 帶有現成的動作，可以連接到Adobe Campaign Standard。

必須發佈Campaign Standard事務性消息及其關聯事件，才能在Journey Orchestration中使用。 如果事件已發佈但消息未發佈，則該消息在Journey Orchestration介面中將不可見。 如果消息已發佈，但其關聯事件未發佈，則消息將在Journey Orchestration介面中可見，但不可用。

>[!NOTE]
>
>一旦建立了Adobe Campaign Standard整合，即自動為Adobe Campaign Standard操作定義每5分鐘4000次呼叫的上限規則。 這與Adobe Campaign Standard事務性資訊的正式規模相符。
>
>閱讀有關中事務性消息傳遞SLA的詳細資訊 [Adobe Campaign Standard產品說明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)。

以下是配置它的步驟：

1. 從 **[!UICONTROL Actions]** 清單，按一下 **[!UICONTROL AdobeCampaignStandard]** 操作。 操作配置窗格在螢幕右側開啟。

   ![](../assets/actioncampaign.png)

1. 複製您的Adobe Campaign Standard實例URL並將其貼上到 **[!UICONTROL URL]** 的子菜單。

1. 按一下 **[!UICONTROL Test the instance URL]** test案件的效力。

   >[!NOTE]
   >
   >此test驗證：
   >
   >主機為&quot;。campaign.adobe.com&quot;、&quot;。campaign-sandbox.adobe.com&quot;、&quot;。campaign-demo.adobe.com&quot;、&quot;。ats.adobe.com&quot;或&quot;。adls.adobe.com&quot;。
   >
   >URL以https開頭，
   >
   >與此Adobe Campaign Standard實例關聯的ORG與Journey Orchestration的ORG相同。

在設計行程時，在 **[!UICONTROL Action]** 類別： **[!UICONTROL Email]**。 **[!UICONTROL Push]**。 **[!UICONTROL SMS]** （請參見） [使用Adobe Campaign操作](../building-journeys/using-adobe-campaign-actions.md))。 **反應事件** 還允許您對消息點擊、開啟等做出反應。 （請參見） [反應事件](../building-journeys/reaction-events.md))。

![](../assets/journey58.png)

如果您使用第三方系統發送消息，則需要添加和配置自定義操作。 請參閱 [關於自定義操作配置](../action/about-custom-action-configuration.md)。
