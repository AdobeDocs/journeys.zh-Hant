---
product: adobe campaign
title: 關於自訂動作組態
description: 了解如何設定自訂動作
feature: Journeys
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 7ce4ddec60f62662d67351b8ca70d7763e76b977
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 15%

---

# 關於自訂動作組態 {#concept_sxy_bzs_dgb}

如果您使用協力廠商系統來傳送訊息，或您想要 [!DNL Journey Orchestration] 若要將API呼叫傳送至協力廠商系統，您可在此設定其連線 [!DNL Journey Orchestration]. 接著，技術使用者定義的自訂動作將可在歷程的左側浮動視窗中使用，位於 **[!UICONTROL Action]** 類別(請參閱 [本頁](../building-journeys/about-action-activities.md). 以下是一些您可透過自訂動作連線至的系統範例：Epsilon、Facebook、Adobe.io、Firebase等
限制列於 [本頁](../about/limitations.md).

以下是設定自訂動作所需的主要步驟：

1. 從 **[!UICONTROL Actions]** 清單，按一下 **[!UICONTROL Add]** 來建立新動作。 動作設定窗格會在畫面右側開啟。

   ![](../assets/custom2.png)

1. 輸入動作的名稱。

   >[!NOTE]
   >
   >請勿使用空格或特殊字元。請勿使用超過 30 個字元。

1. 為動作新增說明。 此步驟為選填。
1. 使用此動作的歷程次數會顯示在 **[!UICONTROL Used in]** 欄位。 您可以按一下 **[!UICONTROL View journeys]** 按鈕，以顯示使用此動作的歷程清單。
1. 定義不同的 **[!UICONTROL URL Configuration]** 參數。 請參閱[此頁面](../action/url-configuration.md)。
1. 設定 **[!UICONTROL Authentication]** 區段。 此設定與資料來源的設定相同。  請參閱[本節](../datasource/external-data-sources.md#section_wjp_nl5_nhb)。
1. 定義 **[!UICONTROL Action parameters]**. 請參閱[此頁面](../action/defining-the-message-parameters.md)。
1. 按一下「**[!UICONTROL Save]**」。

   自訂動作現在已設定完畢，且已準備好用於您的歷程。 請參閱[此頁面](../building-journeys/about-action-activities.md)。

   >[!NOTE]
   >
   >在歷程中使用自訂動作時，大部分參數為唯讀。 您只能修改 **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** 欄位和 **[!UICONTROL Authentication]** 區段。
