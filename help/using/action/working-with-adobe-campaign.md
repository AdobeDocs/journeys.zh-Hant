---
product: adobe campaign
solution: Journey Orchestration
title: 使用 Adobe Campaign
description: 瞭解Adobe Campaign動作
translation-type: tm+mt
source-git-commit: a515e052a5bc1359632a1829df70a206614a5bb2
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 4%

---


# 使用 Adobe Campaign {#using_adobe_campaign_standard}

您可以使用Adobe Campaign Standard的「交易訊息」功能，傳送電子郵件、推播通知和簡訊。

[!DNL Journey Orchestration] 隨附現成可用的動作，可讓您連線至Adobe Campaign Standard。

必須發佈Campaign Standard交易訊息及其相關事件，才能用於歷程協調。 如果活動已發佈但訊息未發佈，則「歷程協調」介面將無法顯示。 如果訊息已發佈，但其相關事件未發佈，則會在「歷程協調」介面中顯示，但無法使用。

>[!NOTE]
>
>一旦設定Adobe Campaign Standard整合，就會自動為Adobe Campaign Standard動作定義每秒13個呼叫的上限規則。 這與Adobe Campaign標準交易訊息的官方規模相符。
>
>閱讀[Adobe Campaign標準產品說明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)中有關交易訊息SLA的更多資訊。

以下是設定它的步驟：

1. 從&#x200B;**[!UICONTROL Actions]**&#x200B;清單中，按一下內建&#x200B;**[!UICONTROL AdobeCampaignStandard]**&#x200B;動作。 動作設定窗格會在畫面的右側開啟。

   ![](../assets/actioncampaign.png)

1. 複製您的Adobe Campaign Standard例項URL，並貼至&#x200B;**[!UICONTROL URL]**&#x200B;欄位。

1. 按一下&#x200B;**[!UICONTROL Test the instance URL]**&#x200B;以測試例項的有效性。

   >[!NOTE]
   >
   >此測試可驗證：
   >
   >主機為&quot;。campaign.adobe.com&quot;、&quot;。campaign-sandbox.adobe.com&quot;或&quot;。campaign-demo.adobe.com&quot;
   >
   >URL以https開頭，
   >
   >與此Adobe Campaign Standard實例關聯的ORG與Journey Orchestration的ORG相同。

在設計您的歷程時，**[!UICONTROL Action]**&#x200B;類別中會提供三個動作：**[!UICONTROL Email]**、**[!UICONTROL Push]**、**[!UICONTROL SMS]**（請參閱[使用Adobe Campaign動作](../building-journeys/using-adobe-campaign-actions.md)）。 **反應** 甚至可讓您對訊息點按、開啟等做出反應。（請參閱[Reactions events](../building-journeys/reaction-events.md)）。

![](../assets/journey58.png)

如果您使用協力廠商系統來傳送訊息，則需要新增及設定自訂動作。 請參閱[關於自訂動作設定](../action/about-custom-action-configuration.md)。
