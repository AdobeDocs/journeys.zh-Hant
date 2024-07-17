---
product: adobe campaign
title: 關於自訂動作組態
description: 瞭解如何設定自訂動作
feature: Journeys
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 7ad2419854b4fcecae7fbb20bdd6a6f2fbc04988
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 12%

---

# 關於自訂動作組態 {#concept_sxy_bzs_dgb}

如果您使用協力廠商系統來傳送訊息，或想要[!DNL Journey Orchestration]傳送API呼叫至協力廠商系統，您可以在此處設定其與[!DNL Journey Orchestration]的連線。 之後，技術使用者定義的自訂動作便可在您歷程的左側浮動視窗中，位於&#x200B;**[!UICONTROL Action]**&#x200B;類別中（請參閱[此頁面](../building-journeys/about-action-activities.md)）。 以下是一些您可以使用自訂動作連線的系統範例：Epsilon、Facebook、Adobe.io、Firebase等。

限制列於[此頁面](../about/limitations.md)。

在自訂動作引數中，您可以傳遞簡單集合以及物件集合。 關於限制，請參閱[此頁面](../usecase/collections.md#limitations)。 另請注意，引數具有預期格式（例如：字串、小數等）。 您必須注意遵守這些預期的格式。 請參閱此[使用案例](../usecase/collections.md)。

以下是設定自訂動作所需的主要步驟：

1. 從&#x200B;**[!UICONTROL Actions]**&#x200B;清單，按一下&#x200B;**[!UICONTROL Add]**&#x200B;以建立新動作。 動作設定窗格會在畫面右側開啟。

   ![](../assets/custom2.png)

1. 輸入動作的名稱。

   >[!NOTE]
   >
   >請勿使用空格或特殊字元。請勿使用超過 30 個字元。

1. 新增說明至您的動作。 此步驟為選填。
1. 使用此動作的歷程次數會顯示在&#x200B;**[!UICONTROL Used in]**&#x200B;欄位中。 您可以按一下&#x200B;**[!UICONTROL View journeys]**&#x200B;按鈕，以顯示使用此動作的歷程清單。
1. 定義不同的&#x200B;**[!UICONTROL URL Configuration]**&#x200B;引數。 請參閱[此頁面](../action/url-configuration.md)。
1. 設定&#x200B;**[!UICONTROL Authentication]**&#x200B;區段。 此設定與資料來源的設定相同。  請參閱[本節](../datasource/external-data-sources.md#section_wjp_nl5_nhb)。
1. 定義&#x200B;**[!UICONTROL Action parameters]**。 請參閱[此頁面](../action/defining-the-message-parameters.md)。
1. 按一下「**[!UICONTROL Save]**」。

   自訂動作現已設定完畢，且可供您在歷程中使用。 請參閱[此頁面](../building-journeys/about-action-activities.md)。

   >[!NOTE]
   >
   >當歷程中使用自訂動作時，大部分引數均為唯讀。 您只能修改&#x200B;**[!UICONTROL Name]**、**[!UICONTROL Description]**、**[!UICONTROL URL]**&#x200B;欄位和&#x200B;**[!UICONTROL Authentication]**&#x200B;區段。
