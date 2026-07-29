---
product: adobe campaign
solution: Journey Orchestration
title: 使用Adobe Campaign v7/v8動作
description: 瞭解Adobe Campaign v7/v8動作
feature: Journeys
role: User
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 44%

---

# 使用 Adobe Campaign v7/v8 {#using_campaign_classic}


>[!CAUTION]
>
>**正在尋找 Adobe Journey Optimizer**？ 按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}以取得 Journey Optimizer 文件。
>
>
>_本文件指的是已由 Journey Optimizer 取代的舊版 Journey Orchestration 資料。 如果您對 Journey Orchestration 或 Journey Optimizer 的存取權有任何疑問，請聯絡您的帳戶團隊。_


如果您有 Adobe Campaign v7 或 v8，則可整合。 其可讓您使用Adobe Campaign異動訊息功能來傳送電子郵件、推播通知及簡訊。

Journey Orchestration 與 Campaign 執行個體之間的連線在佈建時由 Adobe 設定。 聯絡Adobe。

為了讓此功能發揮作用，您需要設定專用動作。 請參閱本[章節](../action/acc-action.md)。

此[區段](../usecase/campaign-classic-use-case.md)中呈現端對端使用案例。

1. 設計您的歷程，從事件開始。 請參閱[本章節](../building-journeys/journey.md)。
1. 在浮動視窗的&#x200B;**動作**&#x200B;區段中，選取行銷活動動作並將其新增至您的歷程。
1. 在&#x200B;**動作引數**&#x200B;中，會顯示訊息裝載中預期的所有欄位。 您需要將每個欄位與您要使用的欄位相對應，無論是從事件還是從資料來源進行。 這類似於自訂動作。 請參閱本[章節](../building-journeys/using-custom-actions.md)。

![](../assets/accintegration2.png)
