---
product: adobe campaign
title: 關於動作
description: 瞭解如何設定動作
feature: Journeys
role: User
level: Intermediate
exl-id: 34f7666b-1c91-4edd-b5d6-4c0513b9c4f3
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 72%

---

# 關於動作 {#about_actions}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_


>[!CONTEXTUALHELP]
>id="jo_actions"
>title="關於動作"
>abstract="您可在此處定義會用於傳送訊息的系統連線，接著，在「動作」類別的歷程左側浮動視窗中，就會顯示此處定義的動作。 "

動作是您向客戶提供個人化即時體驗時使用的連結，這些體驗包含推播通知、電子郵件、簡訊或您在業務中使用的任何其他數位互動方式。

自訂動作可讓您設定協力廠商系統的連線，以傳送訊息或 API 呼叫。您可以使用任何提供者提供的任何服務來設定動作，這些服務可透過具有 JSON 格式的承載，透過 REST API 進行呼叫。

這些動作會顯示在您歷程的左側浮動視窗中，位於&#x200B;**[!UICONTROL Action]**&#x200B;類別中。 請參閱[此頁面](../building-journeys/about-action-activities.md)。

>[!NOTE]
>
>自訂動作的設定一律由&#x200B;**技術使用者**&#x200B;執行。

在 **Actions** 清單中，您可以按下 C 鍵以建立新的歷程、動作、資料來源或事件。如需[!DNL Journey Orchestration]中捷徑的詳細資訊，請參閱[本節](../about/user-interface.md#section_ksq_zr1_ffb)。

若要檢查動作清單或要設定新動作，請按一下頂端功能表的 **[!UICONTROL Actions]**，畫面隨即顯示動作清單。如需介面的詳細資訊，請參閱[此頁面](../about/user-interface.md)。

![](../assets/custom1.png)

如果您有 Adobe Campaign Standard，則需要使用 Adobe Campaign Standard 的「交易訊息」功能來設定立即可用的動作，以便傳送電子郵件、推播通知和簡訊。請參見[此頁面](../action/working-with-adobe-campaign.md)。

如果您有Adobe Campaign v7或v8，則可應要求使用整合。 請參見[此頁面](../action/acc-action.md)。

如果您使用協力廠商系統來傳送訊息，例如 Epsilon、Facebook、Adobe.io、Firebase 等等，則需要新增和設定自訂動作。請參見[此頁面](../action/about-custom-action-configuration.md)。

