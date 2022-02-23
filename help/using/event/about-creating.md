---
product: adobe campaign
title: 建立事件
description: 瞭解如何建立事件
feature: Journeys
role: User
level: Intermediate
exl-id: 2ae8854a-c3e7-469d-9f89-25b54bc3e894
source-git-commit: bdc9ac3f54fae1dfd6f24a54a2687a0834f69c36
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 58%

---

# 建立新事件 {#section_tbk_5qt_pgb}

以下是設定新事件的主要步驟：

1. 在頂端功能表中，按一下 **[!UICONTROL Events]** 索引標籤。畫面隨即顯示事件清單。請參閱 [此頁](../about/user-interface.md) 的上界。

   ![](../assets/journey5.png)

1. 按一下 **[!UICONTROL Add]** 以建立新事件。事件設定窗格會在畫面右側開啟。輸入事件的名稱。也可以添加說明。

   ![](../assets/journey6.png)

   >[!NOTE]
   >
   >請勿使用空格或特殊字元。請勿使用超過 30 個字元。

1. 在 **[!UICONTROL Event ID type]** 欄位中，選擇要使用的事件類型。

   ![](../assets/journey6bis.png)

   * **規則型** 事件：此類型的事件不會產生 eventID。在 **事件ID條件** 欄位中，您只需定義一個規則，系統將使用該規則來標識觸發您的行程的相關事件。 此規則可以根據事件裝載中可用的任何欄位，例如設定檔的位置或新增至設定檔購物車的項目數。

   * **系統生成** 事件：此類型需要eventID。 建立事件時將自動生成此eventID欄位，並將其添加到負載預覽。 推播事件的系統不應產生 ID，而應傳遞有效裝載預覽中可用的 ID。請參閱[本節](../event/previewing-the-payload.md)。
   >[!NOTE]
   >
   >閱讀有關中事件類型的更多資訊 [此部分](../event/about-events.md)。
1. 使用此事件的歷程次數會顯示在 **[!UICONTROL Used in]** 欄位中。您可以按一下 **[!UICONTROL View journeys]** 圖示，以顯示使用此事件的歷程清單。
1. 定義結構和有效負載欄位：您可以在此處選取 [!DNL Journey Orchestration] 預期會收到的事件資訊（通常稱為有效負載）。接著，您就可以在歷程中使用這項資訊。請參閱[此頁面](../event/defining-the-payload-fields.md)。
   >[!NOTE]
   >
   >選擇 **[!UICONTROL System Generated]** 類型，只有具有eventID類型混合的架構可用。 選擇 **[!UICONTROL Rule Based]** 類型，所有體驗事件架構都可用。

1. 對於基於規則的事件，按一下 **[!UICONTROL Event ID condition]** 的子菜單。 使用簡單表達式編輯器，定義系統將用於標識將觸發行程的事件的條件。
   ![](../assets/alpha-event6.png)

   在我們的例子中，我們根據檔案的城市寫了一個條件。 這意味著，每當系統收到與此條件匹配的事件(**[!UICONTROL City]** 欄位和 **[!UICONTROL Paris]** 值)，它會傳遞給Journey Orchestration。

   >[!NOTE]
   >
   >定義高級表達式編輯器時不可用 **[!UICONTROL Event ID condition]**。 在簡單表達式編輯器中，並非所有運算子都可用，它們取決於資料類型。 例如，對於欄位的字串類型，可以使用&quot;contains&quot;或&quot;equal to&quot;。

1. 新增命名空間。此步驟為選填，但建議您新增命名空間，以便運用儲存在「即時客戶個人檔案服務」的資訊。它會定義事件具備的金鑰類型。請參閱[此頁面](../event/selecting-the-namespace.md)。
1. 定義金鑰：從您的有效負載欄位選擇一個欄位，或是定義一個公式以識別與事件相關聯的人員。如果您選取命名空間，系統便會自動設定此金鑰（但您仍可加以編輯）。事實上，[!DNL Journey Orchestration] 會挑選應該與命名空間對應的金鑰（例如，如果您選取電子郵件命名空間，系統便會選取電子郵件金鑰）。請參閱[此頁面](../event/defining-the-event-key.md)。
1. 按一下「**[!UICONTROL Save]**」。

   ![](../assets/journey7.png)

   條件現在已設定完畢，且準備好放入歷程中。若要接收事件，則需要完成其他設定步驟。請參閱[此頁面](../event/additional-steps-to-send-events-to-journey-orchestration.md)。
