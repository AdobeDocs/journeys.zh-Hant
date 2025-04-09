---
product: adobe campaign
title: 關於自訂動作組態
description: 瞭解如何設定自定義動作
feature: Journeys
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 11%

---

# 關於自訂動作組態 {#concept_sxy_bzs_dgb}


>[!CAUTION]
>
>**在尋找 Adobe Systems Journey Optimizer**？ 按兩下這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}以[取得Journey Optimizer 檔。
>
>
>_本檔涉及已被Journey Optimizer 取代的舊版Journey Orchestration資料。 如果您對 Journey Orchestration 或 Journey Optimizer 的訪問許可權有疑問，請連絡您的帳戶團隊。_


如果您使用 協力廠商 系統發送消息，或者想要 [!DNL Journey Orchestration] 向 協力廠商 系統發送 API 調用，則可以在此處配置其連接 [!DNL Journey Orchestration]。 然後，技術用戶定義的自定義作將在旅程 **[!UICONTROL Action]** 的左側調色板類別中可用（請參閱 [此頁面](../building-journeys/about-action-activities.md)。 以下是您可以使用自定義作連接到的一些系統示例：Epsilon、Facebook、Adobe.io、Firebase 等。

此頁面](../about/limitations.md)中[列出了限制。

在自訂動作參數中，您可以傳遞簡單集合以及物件集合。 關於限制，請参閱 [此頁面](../usecase/collections.md#limitations)。 另請注意，參數具有預期的格式 （例如：字串、小數等）。 您必須小心遵守這些預期的格式。 請參閱此 [使用案例](../usecase/collections.md)。

以下是設定自訂作所需的主要步驟：

1. 在 **[!UICONTROL Actions]** 清單中按兩下以 **[!UICONTROL Add]** 創建新作。 作配置窗格在屏幕右側打開。

   ![](../assets/custom2.png)

1. 輸入作的名稱。

   >[!NOTE]
   >
   >請勿使用空格或特殊字元。請勿使用超過 30 個字元。

1. 為作添加說明。 此步驟為選填。
1. 使用此作的歷程數將顯示在 **[!UICONTROL Used in]** 欄位中。 您可以按下 **[!UICONTROL View journeys]** 按鈕以顯示使用此作的歷程清單。
1. 定義不同的 **[!UICONTROL URL Configuration]** 參數。 請參閱[此頁面](../action/url-configuration.md)。
1. 設定區 **[!UICONTROL Authentication]** 段。 此配置與數據源相同。  請參閱[本節](../datasource/external-data-sources.md#section_wjp_nl5_nhb)。
1. **[!UICONTROL Action parameters]**&#x200B;定義 .請參閱[此頁面](../action/defining-the-message-parameters.md)。
1. 按一下「**[!UICONTROL Save]**」。

   自定義作現已配置並準備好在您的旅程中使用。 請參閱[此頁面](../building-journeys/about-action-activities.md)。

   >[!NOTE]
   >
   >在歷程中使用自定義作時，大多數參數都是只讀的。 您只能修改 **[!UICONTROL Name]**、 **[!UICONTROL Description]**、 **[!UICONTROL URL]** 欄位和 section **[!UICONTROL Authentication]** 。
