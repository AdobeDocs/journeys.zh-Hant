---
title: 關於動作
description: 瞭解如何設定動作
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: 87910a9f3dbf2c34776a8d2ab1f00426e8b0704c
workflow-type: ht
source-wordcount: '289'
ht-degree: 100%

---


# 關於動作 {#about_actions}

>[!CONTEXTUALHELP]
>id="jo_actions"
>title="關於動作"
>abstract="您可在此處定義會用於傳送訊息的系統連線，接著，在「動作」類別的歷程左側浮動視窗中，就會顯示此處定義的動作。 "

動作是您向客戶提供個人化即時體驗時使用的連結，這些體驗包含推播通知、電子郵件、簡訊或您在業務中使用的任何其他數位互動方式。

自訂動作可讓您設定協力廠商系統的連線，以傳送訊息或 API 呼叫。您可以使用任何提供者提供的任何服務來設定動作，這些服務可透過具有 JSON 格式的裝載，透過 REST API 進行呼叫。

這些動作會顯示在您歷程的左側浮動視窗中，位於 **[!UICONTROL Action]**&#x200B;類別中 (請參見[](../building-journeys/about-action-activities.md))。

>[!NOTE]
>
>自訂動作的設定一律由&#x200B;**技術使用者**&#x200B;執行。

在&#x200B;**「動作」**&#x200B;清單中，您可以按下 C 鍵以建立新的歷程、動作、資料來源或事件。如需 Journey Orchestration 捷徑的詳細資訊，請參見[](../about/user-interface.md#section_ksq_zr1_ffb)。

若要檢查動作清單或要設定新動作，請按一下頂端選單的「**[!UICONTROL Actions]**」，畫面隨即顯示動作清單。請參見[](../about/user-interface.md)以瞭解介面的詳細資訊。

![](../assets/custom1.png)

如果您有 Adobe Campaign Standard，便需要使用 Adobe Campaign Standard 的「交易訊息」功能來設定立即可用的動作，以便傳送電子郵件、推播通知和簡訊。請參閱[](../action/working-with-adobe-campaign.md)。

如果您使用協力廠商系統來傳送訊息，例如 Epsilon、Facebook、Adobe.io、Firebase 等等，則需要新增和設定自訂動作。請參閱[](../action/about-custom-action-configuration.md)。

如需如何設定 Journey Orchestration 的動作以及如何在歷程中使用動作的詳細資訊，請觀看此[教影片教學課程](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/configure-actions.html)。
