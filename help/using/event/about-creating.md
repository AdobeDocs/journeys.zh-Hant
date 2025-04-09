---
product: adobe campaign
title: 建立事件
description: 瞭解如何建立事件
feature: Journeys
role: User
level: Intermediate
exl-id: 2ae8854a-c3e7-469d-9f89-25b54bc3e894
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 47%

---

# 建立新事件 {#section_tbk_5qt_pgb}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_


以下是設定新事件的主要步驟：

1. 在頂端功能表中，按一下 **[!UICONTROL Events]** 索引標籤。畫面隨即顯示事件清單。如需介面的詳細資訊，請參閱[此頁面](../about/user-interface.md)。

   ![](../assets/journey5.png)

1. 按一下 **[!UICONTROL Add]** 以建立新事件。事件設定窗格會在畫面右側開啟。 輸入事件的名稱。 您也可以新增說明。

   ![](../assets/journey6.png)

   >[!NOTE]
   >
   >請勿使用空格或特殊字元。請勿使用超過 30 個字元。

1. 在&#x200B;**[!UICONTROL Event ID type]**&#x200B;欄位中，選取您要使用的事件型別。

   ![](../assets/journey6bis.png)

   * **規則型** 事件：此類型的事件不會產生 eventID。在&#x200B;**事件ID條件**&#x200B;欄位中，您只需定義一個規則，系統會使用該規則來識別將觸發您歷程的相關事件。 此規則可以根據事件裝載中可用的任何欄位，例如輪廓的位置或新增至輪廓購物車的項目數。

   * **系統產生的**&#x200B;事件：此型別需要eventID。 建立事件時會自動產生此eventID欄位，並將其新增至裝載預覽。 推播事件的系統不應產生ID，而應傳遞有效負載預覽中可用的ID。 請參閱[本節](../event/previewing-the-payload.md)。

   >[!NOTE]
   >
   >閱讀有關[本節](../event/about-events.md)中事件型別的詳細資訊。
1. 使用此事件的歷程次數會顯示在 **[!UICONTROL Used in]** 欄位中。您可以按一下 **[!UICONTROL View journeys]** 圖示，以顯示使用此事件的歷程清單。
1. 定義結構和有效負載欄位：您可以在此處選取 [!DNL Journey Orchestration] 預期會收到的事件資訊（通常稱為有效負載）。接著，您就可以在歷程中使用這項資訊。請參閱[此頁面](../event/defining-the-payload-fields.md)。
   >[!NOTE]
   >
   >當您選取&#x200B;**[!UICONTROL System Generated]**&#x200B;型別時，只有具有eventID型別mixin的結構描述才可使用。 當您選取&#x200B;**[!UICONTROL Rule Based]**&#x200B;型別時，所有體驗事件結構描述都可使用。

1. 對於規則型事件，請在&#x200B;**[!UICONTROL Event ID condition]**欄位內按一下。 使用簡單運算式編輯器，定義系統將使用的條件，以識別將觸發您歷程的事件。
   ![](../assets/alpha-event6.png)

   在我們的範例中，我們根據設定檔的城市來撰寫條件。 這表示每當系統收到符合此條件（**[!UICONTROL City]**&#x200B;欄位和&#x200B;**[!UICONTROL Paris]**&#x200B;值）的事件時，都會將其傳遞至Journey Orchestration。

   >[!NOTE]
   >
   >定義&#x200B;**[!UICONTROL Event ID condition]**&#x200B;時，無法使用進階運算式編輯器。 在簡單運算式編輯器中，並非所有運運算元都可使用，它們取決於資料型別。 例如，對於欄位的字串型別，您可以使用「包含」或「等於」。

1. 新增命名空間。此步驟為選填，但建議您新增命名空間，以便運用儲存在「即時客戶輪廓服務」的資訊。它會定義事件具備的金鑰類型。請參閱[此頁面](../event/selecting-the-namespace.md)。
1. 定義金鑰：從您的有效負載欄位選擇一個欄位，或是定義一個公式以識別與事件相關聯的人員。如果您選取命名空間，系統便會自動設定此金鑰（但您仍可加以編輯）。事實上，[!DNL Journey Orchestration] 會挑選應該與命名空間對應的金鑰（例如，如果您選取電子郵件命名空間，系統便會選取電子郵件金鑰）。請參閱[此頁面](../event/defining-the-event-key.md)。
1. 按一下「**[!UICONTROL Save]**」。

   ![](../assets/journey7.png)

   條件現在已設定完畢，且準備好放入歷程中。若要接收事件，則需要完成其他設定步驟。請參閱[此頁面](../event/additional-steps-to-send-events-to-journey-orchestration.md)。
