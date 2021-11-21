---
product: adobe campaign
title: 設定資料來源
description: 了解如何為歷程進階使用案例設定資料來源
feature: Journeys
role: User
level: Intermediate
exl-id: 2cfa4397-fe8f-44b3-b219-2fd5d3bdd156
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 15%

---

# 設定資料來源 {#concept_vml_hdy_w2b}

在我們的使用案例中，我們想要將個人化資料用於訊息。 我們也需要檢查該人員是否為忠誠會員，且過去24小時內未與其聯絡。 此資訊會儲存在即時客戶設定檔資料庫中。 此 **技術使用者** 需要設定Adobe Experience Platform資料來源以擷取這些欄位。

有關資料源配置的其他資訊，請參閱 [本頁](../datasource/about-data-sources.md).

1. 在菜單窗格中，選擇 **[!UICONTROL Admin]**. 在 **[!UICONTROL Data sources]** ，按一下 **[!UICONTROL Manage]**.
1. 選取內建的Adobe Experience Platform資料來源。

   ![](../assets/journey23.png)

1. 在預先設定的群組欄位中，檢查是否已選取下列欄位：

   * _person > name > firstName_
   * _person > name > lastName_
   * _個人電子郵件>地址_

1. 按一下 **[!UICONTROL Add a New Field Group]**，選取 **[!UICONTROL Profiles]** 架構和新增 **忠誠會員** 欄位中取得。 此 **忠誠會員** 欄位是自訂欄位，已新增至XDM:&quot;_customer > marlton > loyatyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. 按一下 **[!UICONTROL Add a New Field Group]**，請選取 **[!UICONTROL ExperienceEvent]** 架構，並針對指定期間內傳送的訊息數量，選取條件所需的欄位： _timestamp_ 日期和 _directMarketing >傳送>值_ ，以了解已傳送的訊息數量。

   ![](../assets/journeyuc2_7.png)

1. 按一下「**[!UICONTROL Save]**」。

我們還需要檢查該人在酒店預訂系統中是否有預訂。 此 **技術使用者** 需要設定第二個資料來源以擷取此欄位。

1. 在資料來源清單中，按一下 **[!UICONTROL Add]** 新增外部資料來源以定義與酒店訂房系統的連線。

   ![](../assets/journeyuc2_9.png)

1. 輸入資料來源的名稱和外部服務的URL，例如： _https://marlton.com/reservation_

   >[!CAUTION]
   >
   >基於安全考量，我們強烈建議您使用 HTTPS。

1. 根據外部服務配置設定身份驗證：**[!UICONTROL No authentication]**、**[!UICONTROL Basic]**、**[!UICONTROL Custom]** 或 **[!UICONTROL API key]**。在範例中，我們為類型選擇「基本」，並指定API呼叫的使用者名稱和密碼。

   ![](../assets/journeyuc2_10.png)

1. 按一下 **[!UICONTROL Add a New Field Group]** 定義要擷取的資訊和API參數。 例如，只有一個參數(id)，因此我們需要建立一個欄位群組，其中包含下列資訊：

   * **[!UICONTROL Method]**：選取 POST 或 GET 方法。在本例中，我們選取 GET 方法。
   * **[!UICONTROL Response Payload]**:按一下內部 **[!UICONTROL Payload]** 欄位並貼上裝載的範例。 確認欄位類型是否正確。每次呼叫 API 時，系統都會擷取有效負載範例中包含的所有欄位。在我們的範例中，裝載僅包含訂房狀態：

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamic Values]**:在範例中，輸入與用來識別每個客戶之金鑰對應的參數，即「id」。 此參數的值將在歷程中定義。

   ![](../assets/journeyuc2_11.png)

1. 按一下「**[!UICONTROL Save]**」。

   資料來源現在已完成設定，且可供您在歷程中使用。
