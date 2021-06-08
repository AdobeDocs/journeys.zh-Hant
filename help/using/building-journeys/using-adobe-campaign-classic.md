---
product: adobe campaign
solution: Journey Orchestration
title: 使用Adobe Campaign v7/v8動作
description: 了解Adobe Campaign v7/v8動作
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: b2439788ef547b401dea64faf46d4398b9a1a0c7
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---

# 使用Adobe Campaign v7/v8 {#using_campaign_classic}

如果您有Adobe Campaign v7或v8，則可使用整合。 它可讓您使用Adobe Campaign交易訊息功能來傳送電子郵件、推播通知和簡訊。

Journey Orchestration與促銷活動例項之間的連線是在布建時Adobe所設定。 聯繫Adobe。

若要讓此功能發揮作用，您需要設定專用的動作。 請參閱此[節](../action/acc-action.md)。

此[section](../usecase/campaign-classic-use-case.md)中顯示了端到端使用案例。

1. 從事件開始，設計您的歷程。 請參閱此[節](../building-journeys/journey.md)。
1. 在浮動視窗的&#x200B;**Action**&#x200B;區段中，選取Campaign動作，並將其新增至您的歷程。
1. 在&#x200B;**動作參數**&#x200B;中，會顯示訊息裝載中預期的所有欄位。 您需要將每個欄位對應至您要使用的欄位，不論是來自事件或來自資料來源。 這類似於自訂動作。 請參閱此[節](../building-journeys/using-custom-actions.md)。

![](../assets/accintegration2.png)
