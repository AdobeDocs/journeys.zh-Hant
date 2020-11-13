---
title: 關於自訂動作組態
description: 瞭解如何設定自訂動作
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 9fc7f0664afa19e3debe2ad4f37d6b794da0ed1f
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 15%

---


# 關於自訂動作組態 {#concept_sxy_bzs_dgb}

如果您使用協力廠商系統來傳送訊息，或如果您要傳送 [!DNL Journey Orchestration] API呼叫至協力廠商系統，您就可在此設定其連線 [!DNL Journey Orchestration]。 然後，技術使用者定義的自訂動作就會出現在您旅程的左側浮動視窗中，位於類別中(請 **[!UICONTROL Action]** 參閱 [本頁](../building-journeys/about-action-activities.md))。 以下是一些您可以使用自訂動作來連接的系統範例：Epsilon、Facebook、Adobe.io、Firebase等
本頁列出了 [限制](../about/limitations.md)。

以下是設定自訂動作所需的主要步驟：

1. 從清單 **[!UICONTROL Actions]** 中，按一 **[!UICONTROL Add]** 下以建立新動作。 動作設定窗格會在畫面的右側開啟。

   ![](../assets/custom2.png)

1. 輸入動作的名稱。

   >[!NOTE]
   >
   >請勿使用空格或特殊字元。請勿使用超過 30 個字元。

1. 將描述新增至您的動作。 此步驟為選填。
1. The number of journeys that use this action is displayed in the **[!UICONTROL Used in]** field. You can click the **[!UICONTROL View journeys]** button to display the list of  journeys using this action.
1. Define the different **[!UICONTROL URL Configuration]** parameters. 請參閱[本頁](../action/url-configuration.md)。
1. 設定區 **[!UICONTROL Authentication]** 段。 此設定與資料來源的設定相同。  請參閱[本區段](../datasource/external-data-sources.md#section_wjp_nl5_nhb)。
1. 定義 **[!UICONTROL Message parameters]**。 請參閱[本頁](../action/defining-the-message-parameters.md)。
1. 按一下 **[!UICONTROL Save]**。

   自訂動作現在已設定好，可供您在歷程中使用。 請參閱[本頁](../building-journeys/about-action-activities.md)。

   >[!NOTE]
   >
   >在歷程中使用自訂動作時，大部分參數都是唯讀的。 您只能修改、 **[!UICONTROL Name]**、 **[!UICONTROL Description]**、 **[!UICONTROL URL]** 欄位和節 **[!UICONTROL Authentication]** 。
