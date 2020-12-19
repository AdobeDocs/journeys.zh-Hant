---
product: adobe campaign
solution: Journey Orchestration
title: 使用 Adobe Campaign 動作
description: 瞭解Adobe Campaign動作
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '899'
ht-degree: 5%

---


# 使用 Adobe Campaign 動作 {#using_campaign_action}

如果您有Adobe Campaign Standard，則可使用下列現成可用的動作：**[!UICONTROL Email]**、**[!UICONTROL Push]**&#x200B;和&#x200B;**[!UICONTROL SMS]**。

>[!NOTE]
>
>為此，您需要配置內置操作。 請參見[此頁面](../action/working-with-adobe-campaign.md)。

對於這些通道，您可以選擇Adobe Campaign Standard交易訊息&#x200B;**範本**。 事實上，[!DNL Journey Orchestration]並非訊息傳送解決方案。 對於內建的電子郵件、簡訊和推播通道，我們依賴交易式訊息來執行訊息傳送。 這表示，如果您想在歷程中使用特定訊息範本，您必須在Adobe Campaign Standard中發佈。 請參閱[本頁](https://docs.adobe.com/content/help/zh-Hant/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)瞭解如何使用此功能。

>[!NOTE]
>
>必須發佈Campaign Standard交易訊息及其相關事件，才能用於歷程協調。 如果活動已發佈但訊息未發佈，則「歷程協調」介面將無法顯示。 如果訊息已發佈，但其相關事件未發佈，則會在「歷程協調」介面中顯示，但無法使用。

![](../assets/journey59.png)

您可以使用事件（也稱為即時）或描述檔交易訊息範本。

>[!NOTE]
>
>當我們傳送即時交易訊息(rtEvent)，或當我們透過自訂動作傳送訊息給協力廠商系統時，系統需要特定的設定，才能進行疲勞、區塊清單或取消訂閱管理。 例如，如果「取消訂閱」屬性儲存在Adobe Experience Platform或協力廠商系統中，則必須在傳送訊息前新增條件，才能檢查此條件。

選擇模板時，消息裝載中預期的所有欄位都顯示在&#x200B;**[!UICONTROL Address]**&#x200B;和&#x200B;**[!UICONTROL Personalization Data]**&#x200B;下的活動配置窗格中。 您需要將每個欄位對應至您要使用的欄位，不論是來自事件或來自資料來源。 您也可以使用進階運算式編輯器手動傳遞值、對擷取的資訊執行資料控制（例如將字串轉換為大寫），或使用函式，例如&quot;if, then, else&quot;。 請參閱[本頁](../expression/expressionadvanced.md)。

![](../assets/journey60.png)

## 電子郵件和簡訊{#section_asc_51g_nhb}

對於&#x200B;**[!UICONTROL Email]**&#x200B;和&#x200B;**[!UICONTROL SMS]**，參數是相同的。

>[!NOTE]
>
>對於電子郵件，如果您使用設定檔交易範本，取消訂閱機制會由Campaign Standard立即處理。 您只需在範本中新增&#x200B;**[!UICONTROL Unsubscription link]**&#x200B;內容區塊（[瞭解詳細內容](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)）。 如果您使用事件型範本(rtEvent)，您需要在訊息中新增將該人員的電子郵件傳遞至URL參數並指向取消訂閱登陸頁面的連結。 您必須建立此登陸頁面，並確定該人員取消訂閱的決定已傳送至Adobe。

首先，您需要選擇事務性消息傳遞模板。 請參見[此頁面](../building-journeys/about-action-activities.md)。

有兩種類別可供使用：**[!UICONTROL Address]**&#x200B;和&#x200B;**[!UICONTROL Personalization Data]**。

您可以輕鬆定義使用介面檢索&#x200B;**[!UICONTROL Address]**&#x200B;或&#x200B;**[!UICONTROL Personalization Data]**&#x200B;的位置。 您可以瀏覽事件和可用資料來源的欄位。 您也可以使用進階運算式編輯器，來處理更進階的使用案例，例如使用需要傳遞參數或執行操作的資料來源。 請參閱[本頁](../expression/expressionadvanced.md)。

**[!UICONTROL Address]**

>[!NOTE]
>
>只有在您選擇「事件」事務性訊息時，才會顯示此類別。 對於「描述檔」訊息，系統會自動從Adobe Campaign Standard擷取&#x200B;**[!UICONTROL Address]**&#x200B;欄位。

這些是系統需要知道消息發送位置的欄位。 對於電子郵件範本，此範本是電子郵件地址。 對於SMS來說，這是手機號碼。

![](../assets/journey61.png)

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>您無法在個人化資料中傳遞系列。 如果交易式電子郵件或SMS需要收藏集，則無法運作。 另請注意，個人化資料具有預期的格式(例如：字串、小數等)。 您必須謹慎遵守這些預期格式。

這些是Adobe Campaign Standard訊息所預期的欄位。 這些欄位可用來個人化訊息、套用條件式格式，或選擇特定的訊息變體。

![](../assets/journey62.png)

## 推送{#section_im3_hvf_nhb}

在使用推播活動之前，您的行動應用程式必須與Campaign Standard一起設定，才能傳送推播通知。 請使用此[文章](https://helpx.adobe.com/tw/campaign/kb/integrate-mobile-sdk.html)來執行行動裝置的必要實作步驟。

首先，您必須從下拉式清單和交易式訊息中選擇行動應用程式。 請參閱[本頁](../building-journeys/about-action-activities.md)。

![](../assets/journey62bis.png)

有兩種類別可供使用：**[!UICONTROL Target]**&#x200B;和&#x200B;**[!UICONTROL Personalization Data]**。

**[!UICONTROL Target]**

>[!NOTE]
>
>只有在您選擇事件消息時，才會顯示此類別。 對於描述檔訊息，系統會使用Adobe Campaign Standard所執行的協調功能，自動擷取&#x200B;**[!UICONTROL Target]**&#x200B;欄位。

在本節中，您需要定義&#x200B;**[!UICONTROL Push platform]**。 下拉式清單可讓您選取&#x200B;**[!UICONTROL Apple Push Notification Server]**(iOS)或&#x200B;**[!UICONTROL Firebase Cloud Messaging]**(Android)。 您也可以從事件或資料來源中選取特定欄位，或定義進階運算式。

您也需要定義&#x200B;**[!UICONTROL Registration Token]**。 運算式取決於在事件裝載或其他[!DNL Journey Orchestration]資訊中定義Token的方式。 它可以是簡單欄位或更複雜的運算式，例如在系列中定義代號：

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>您無法在個人化資料中傳遞系列。 如果交易式推播期望系列，則無法運作。 另請注意，個人化資料具有預期的格式(例如：字串、小數等)。 您必須謹慎遵守這些預期格式。

這些是Adobe Campaign Standard訊息中使用的交易範本所預期的欄位。 這些欄位可用來個人化您的訊息、套用條件式格式，或選擇特定的訊息變體。
