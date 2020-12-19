---
product: adobe campaign
solution: Journey Orchestration
title: 建立事件
description: 瞭解如何建立活動
translation-type: tm+mt
source-git-commit: b3ed5d305ddd1c86814373fc923390dc50a80c7e
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 53%

---


# 建立新事件{#section_tbk_5qt_pgb}

以下是設定新事件的主要步驟：

1. 在頂端功能表中，按一下 **[!UICONTROL Events]** 索引標籤。畫面隨即顯示事件清單。有關介 [面的詳細資訊](../about/user-interface.md) ，請參閱本頁。

   ![](../assets/journey5.png)

1. 按一下 **[!UICONTROL Add]** 以建立新事件。事件設定窗格會在畫面右側開啟。輸入事件的名稱。您也可以新增說明。

   ![](../assets/journey6.png)

   >[!NOTE]
   >
   >請勿使用空格或特殊字元。請勿使用超過 30 個字元。

1. 在欄位 **[!UICONTROL Event ID type]** 中，選取您要使用的事件類型。

   ![](../assets/journey6bis.png)

   * **規則型事件** :此類型的事件不會產生eventID。 在「事 **件ID條件** 」欄位中，您只需定義規則，系統將使用該規則來識別將觸發歷程的相關事件。 此規則可以根據事件裝載中可用的任何欄位，例如描述檔位置或新增至描述檔購物車的項目數。

   * **系統產生的事件** :此類型需要eventID。 建立事件時會自動產生此eventID欄位，並新增至裝載預覽。 推送事件的系統不應產生ID，而應傳遞裝載預覽中可用的ID。 請參閱[本區段](../event/previewing-the-payload.md)。
   >[!NOTE]
   >
   >閱讀本節中更多有關事件 [類型的資訊](../event/about-events.md)。
1. 使用此事件的歷程次數會顯示在 **[!UICONTROL Used in]** 欄位中。您可以按一下 **[!UICONTROL View journeys]** 圖示，以顯示使用此事件的歷程清單。
1. 定義結構和有效負載欄位：您可以在此處選取 [!DNL Journey Orchestration] 預期會收到的事件資訊（通常稱為有效負載）。接著，您就可以在歷程中使用這項資訊。請參閱[本頁](../event/defining-the-payload-fields.md)。
   >[!NOTE]
   >
   >選擇類型時， **[!UICONTROL System Generated]** 只有具有eventID類型混合的架構可用。 選擇類型時，所 **[!UICONTROL Rule Based]** 有「體驗事件」結構都可用。

1. 對於規則型事件，請按一下欄位內 **[!UICONTROL Event ID condition]** 部。 使用簡單運算式編輯器，定義系統將用來識別將觸發您旅程的事件的條件。
   ![](../assets/alpha-event6.png)

   在我們的例子中，我們根據個人檔案的城市寫了一個條件。 這表示每當系統收到符合此條件（欄位和值）的&#x200B;**[!UICONTROL City]** 事件時， **[!UICONTROL Paris]** 就會將它傳送至「歷程協調」。

1. 新增命名空間。此步驟為選填，但建議您新增命名空間，以便運用儲存在「即時客戶個人檔案服務」的資訊。它會定義事件具備的金鑰類型。請參閱[本頁](../event/selecting-the-namespace.md)。
1. 定義金鑰：從您的有效負載欄位選擇一個欄位，或是定義一個公式以識別與事件相關聯的人員。如果您選取命名空間，系統便會自動設定此金鑰（但您仍可加以編輯）。事實上，[!DNL Journey Orchestration] 會挑選應該與命名空間對應的金鑰（例如，如果您選取電子郵件命名空間，系統便會選取電子郵件金鑰）。請參閱[本頁](../event/defining-the-event-key.md)。
1. 對於系統產生的事件，您可以新增條件。 此步驟為選填。這可讓系統僅處理符合條件的事件。您只能根據事件含有之資訊設定條件。請參閱[本頁](../event/adding-a-condition.md)。
1. 按一下 **[!UICONTROL Save]**。

   ![](../assets/journey7.png)

   條件現在已設定完畢，且準備好放入歷程中。若要接收事件，則需要完成其他設定步驟。請參閱[本頁](../event/additional-steps-to-send-events-to-journey-orchestration.md)。