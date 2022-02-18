---
product: adobe campaign
title: 使用 Adobe Campaign 動作
description: 瞭解Adobe Campaign操作
feature: Journeys
role: User
level: Intermediate
source-git-commit: 2195ee3863b38ead504eb6785ceb3c37735fade9
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 5%

---

# 使用 Adobe Campaign Standard {#using_campaign_action}

如果您有Adobe Campaign Standard，則可以執行以下現成操作活動： **[!UICONTROL Email]**。 **[!UICONTROL Push]** 和 **[!UICONTROL SMS]**。

>[!NOTE]
>
>為此，您需要配置內置操作。 請參見[此頁面](../action/working-with-adobe-campaign.md)。

對於這些渠道，您選擇一個Adobe Campaign Standard事務性消息 **模板**。 的確， [!DNL Journey Orchestration] 不是消息發送解決方案。 對於內置的電子郵件、簡訊和推送通道，我們依靠事務性消息來執行消息發送。 這意味著，如果要在您的行程中使用某個消息模板，則必須在Adobe Campaign Standard發佈該模板。 請參閱 [此頁](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=zh-Hant) 瞭解如何使用此功能。

>[!NOTE]
>
>必須發佈Campaign Standard事務性消息及其關聯事件，才能在Journey Orchestration中使用。 如果事件已發佈但消息未發佈，則該消息在Journey Orchestration介面中將不可見。 如果消息已發佈，但其關聯事件未發佈，則消息將在Journey Orchestration介面中可見，但不可用。

![](../assets/journey59.png)

可以使用事件（也稱為即時）或配置檔案事務性消息傳遞模板。

>[!NOTE]
>
>當我們發送即時事務性消息(rtEvent)或通過自定義操作將消息路由到第三方系統時，需要特定設定來進行已多次聯繫、阻止清單或取消訂閱管理。 例如，如果「unsubscribe」屬性儲存在Adobe Experience Platform或第三方系統中，則必須在消息發送前添加條件以檢查此條件。

選擇模板時，消息負載中預期的所有欄位都將顯示在活動配置窗格中的 **[!UICONTROL Address]** 和 **[!UICONTROL Personalization Data]**。 您需要將每個欄位與要使用的欄位進行映射，無論是從事件還是從資料源。 您還可以使用高級表達式編輯器手動傳遞值，對檢索到的資訊執行資料處理（例如，將字串轉換為大寫），或使用諸如&quot;if, then, else&quot;之類的函式。 請參閱[此頁面](../expression/expressionadvanced.md)。

![](../assets/journey60.png)

## 電子郵件和簡訊 {#section_asc_51g_nhb}

對於 **[!UICONTROL Email]** 和 **[!UICONTROL SMS]**，參數相同。

>[!NOTE]
>
>對於電子郵件，如果您使用的是配置檔案事務模板，則取消訂閱機制將通過Campaign Standard進行現成處理。 只需添加 **[!UICONTROL Unsubscription link]** 模板中的內容塊([瞭解更多](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html))。 如果使用基於事件的模板(rtEvent)，則需要在消息中添加一個連結，該連結在URL參數中傳遞人員的電子郵件並指向未訂閱登錄頁。 您需要建立此登錄頁，並確保將人員取消訂閱的決定傳輸到Adobe。

首先，您需要選擇事務性消息傳送模板。 請參見[此頁面](../building-journeys/about-action-activities.md)。

有兩種類別： **[!UICONTROL Address]** 和 **[!UICONTROL Personalization Data]**。

您可以輕鬆定義檢索位置 **[!UICONTROL Address]** 或 **[!UICONTROL Personalization Data]** 使用介面。 您可以瀏覽事件和可用資料源的欄位。 您還可以使用高級表達式編輯器進行更高級的使用情形，例如使用需要傳遞參數或執行操作的資料源。 請參閱[此頁面](../expression/expressionadvanced.md)。

**[!UICONTROL Address]**

>[!NOTE]
>
>僅當選擇「事件」事務性消息時，此類別才可見。 對於「配置檔案」消息， **[!UICONTROL Address]** 欄位由系統自動從Adobe Campaign Standard檢索。

這些是系統需要知道在何處發送消息的欄位。 對於電子郵件模板，它是電子郵件地址。 對於簡訊，是手機號碼。

![](../assets/journey61.png)

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>無法在個性化資料中傳遞集合。 如果事務性電子郵件或SMS需要集合，則它將無法工作。 另請注意，個性化資料具有預期格式(示例：字串、小數等)。 您必須小心遵守這些預期格式。

這些是Adobe Campaign Standard消息所需的欄位。 這些欄位可用於個性化消息、應用條件格式或選擇特定消息變型。

![](../assets/journey62.png)

## 推播 {#section_im3_hvf_nhb}

在使用推送活動之前，需要配置您的移動應用，並配置Campaign Standard來發送推送通知。 使用此 [文章](https://helpx.adobe.com/tw/campaign/kb/integrate-mobile-sdk.html) 為移動設備採取必要的實施步驟。

首先，您需要從下拉清單和事務性消息中選擇移動應用。 請參閱[此頁面](../building-journeys/about-action-activities.md)。

![](../assets/journey62bis.png)

有兩種類別： **[!UICONTROL Target]** 和 **[!UICONTROL Personalization Data]**。

**[!UICONTROL Target]**

>[!NOTE]
>
>僅當選擇事件消息時，此類別才可見。 對於配置檔案消息， **[!UICONTROL Target]** 系統使用Adobe Campaign Standard執行的協調自動檢索欄位。

在本節中，您需要定義 **[!UICONTROL Push platform]**。 下拉清單允許您選擇 **[!UICONTROL Apple Push Notification Server]** (iOS或 **[!UICONTROL Firebase Cloud Messaging]** (Android)。 您也可以從事件或資料源中選擇特定欄位，或定義高級表達式。

您還需要定義 **[!UICONTROL Registration Token]**。 表達式取決於在事件負載或其他負載中如何定義令牌 [!DNL Journey Orchestration] 的下界。 它可以是簡單欄位或更複雜的表達式，如果令牌在集合中定義，例如：

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>無法在個性化資料中傳遞集合。 如果事務推送需要收集，則它不會工作。 另請注意，個性化資料具有預期格式(示例：字串、小數等)。 您必須小心遵守這些預期格式。

這些是您的Adobe Campaign Standard消息中使用的事務模板所需的欄位。 這些欄位可用於個性化您的消息、應用條件格式或選擇特定的消息變型。
