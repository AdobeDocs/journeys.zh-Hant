---
product: adobe campaign
title: 關於自訂動作組態
description: 了解如何設定自訂動作
feature: 歷程
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 15%

---

# 關於自訂動作組態 {#concept_sxy_bzs_dgb}

如果您使用協力廠商系統來傳送訊息，或您想要[!DNL Journey Orchestration]將API呼叫傳送至協力廠商系統，您可在此設定其與[!DNL Journey Orchestration]的連線。 接著，技術使用者定義的自訂動作便可在您歷程的左側浮動視窗中取得，位於&#x200B;**[!UICONTROL Action]**&#x200B;類別中（請參閱[此頁面](../building-journeys/about-action-activities.md)）。 以下是一些您可透過自訂動作連線至的系統範例：Epsilon、Facebook、Adobe.io、Firebase等
[此頁面](../about/limitations.md)列出限制。

以下是設定自訂動作所需的主要步驟：

1. 從&#x200B;**[!UICONTROL Actions]**&#x200B;清單中，按一下&#x200B;**[!UICONTROL Add]**&#x200B;以建立新操作。 動作設定窗格會在畫面右側開啟。

   ![](../assets/custom2.png)

1. 輸入動作的名稱。

   >[!NOTE]
   >
   >請勿使用空格或特殊字元。請勿使用超過 30 個字元。

1. 為動作新增說明。 此步驟為選填。
1. 使用此動作的歷程次數會顯示在&#x200B;**[!UICONTROL Used in]**&#x200B;欄位中。 您可以按一下&#x200B;**[!UICONTROL View journeys]**&#x200B;按鈕，以顯示使用此動作的歷程清單。
1. 定義不同的&#x200B;**[!UICONTROL URL Configuration]**&#x200B;參數。 請參閱[此頁面](../action/url-configuration.md)。
1. 配置&#x200B;**[!UICONTROL Authentication]**&#x200B;部分。 此設定與資料來源的設定相同。  請參閱[本節](../datasource/external-data-sources.md#section_wjp_nl5_nhb)。
1. 定義&#x200B;**[!UICONTROL Message parameters]**。 請參閱[此頁面](../action/defining-the-message-parameters.md)。
1. 按一下「**[!UICONTROL Save]**」。

   自訂動作現在已設定完畢，且已準備好用於您的歷程。 請參閱[此頁面](../building-journeys/about-action-activities.md)。

   >[!NOTE]
   >
   >在歷程中使用自訂動作時，大部分參數為唯讀。 您只能修改&#x200B;**[!UICONTROL Name]**、**[!UICONTROL Description]**、**[!UICONTROL URL]**&#x200B;欄位和&#x200B;**[!UICONTROL Authentication]**&#x200B;區段。
