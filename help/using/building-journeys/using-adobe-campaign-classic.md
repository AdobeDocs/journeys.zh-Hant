---
product: adobe campaign
solution: Journey Orchestration
title: 使用 Adobe Campaign v7/v8 動作
description: 瞭解 v7/v8 Adobe Campaign動作
feature: Journeys
role: User
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 13%

---

# 使用 Adobe Campaign v7/v8 {#using_campaign_classic}


>[!CAUTION]
>
>**在尋找 Adobe Systems Journey Optimizer**？ 按兩下這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}以[取得Journey Optimizer 檔。
>
>
>_本檔涉及已被Journey Optimizer 取代的舊版Journey Orchestration資料。 如果您對 Journey Orchestration 或 Journey Optimizer 的訪問許可權有疑問，請連絡您的帳戶團隊。_


如果您有 Adobe Campaign v7 或 v8，則可整合。 它將允許您使用Adobe Campaign交易消息傳遞功能發送電子郵件，推送通知和SMS。

Journey Orchestration 實例和Campaign實例之間的連接是在預置時通過Adobe Systems設置的。 聯絡Adobe Systems。

為此，您需要配置專用作。 請參閱本[章節](../action/acc-action.md)。

本節[](../usecase/campaign-classic-use-case.md)介紹了端到端用例。

1. 設計您的旅程，從事件開始。 請參閱[本章節](../building-journeys/journey.md)。
1. 在調色板的“ **作** ”部分中，選擇一個Campaign作並將其添加到您的旅程中。
1. **在 Action 參數**&#x200B;中，將顯示消息負載中所需的所有欄位。您需要從事件或資料來源將每個字段與要使用的欄位對應。 這類似於自定義作。 請參閱本[章節](../building-journeys/using-custom-actions.md)。

![](../assets/accintegration2.png)
