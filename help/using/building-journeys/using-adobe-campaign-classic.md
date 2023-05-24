---
product: adobe campaign
solution: Journey Orchestration
title: 使用Adobe Campaignv7/v8操作
description: 瞭解Adobe Campaignv7/v8操作
feature: Journeys
role: User
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 26%

---

# 使用 Adobe Campaign v7/v8 {#using_campaign_classic}

如果您有 Adobe Campaign v7 或 v8，則可整合。 它允許您使用Adobe Campaign事務性消息傳遞功能發送電子郵件、推送通知和簡訊。

Journey Orchestration 與 Campaign 執行個體之間的連線在佈建時由 Adobe 設定。聯繫Adobe。

要使此操作正常運行，您需要配置專用操作。 請參閱本[章節](../action/acc-action.md)。

本中介紹了端到端使用案例 [節](../usecase/campaign-classic-use-case.md)。

1. 設計您的旅程，從活動開始。 請參閱[本章節](../building-journeys/journey.md)。
1. 在 **操作** 頁籤，選擇「市場活動」活動並將其添加到您的行程中。
1. 在 **操作參數**，將顯示消息負載中所需的所有欄位。 您需要將每個欄位與要使用的欄位進行映射，無論是從事件還是從資料源。 這類似於自定義操作。 請參閱本[章節](../building-journeys/using-custom-actions.md)。

![](../assets/accintegration2.png)
