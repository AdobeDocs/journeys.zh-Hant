---
product: adobe campaign
title: 設定資料來源
description: 瞭解如何設定歷程進階使用案例的資料來源
feature: Journeys
role: User
level: Intermediate
exl-id: 2cfa4397-fe8f-44b3-b219-2fd5d3bdd156
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 12%

---

# 設定資料來源 {#concept_vml_hdy_w2b}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_


在我們的使用案例中，我們希望對訊息使用個人化資料。 我們還需要檢查該人士是否為忠誠會員，且在過去24小時內未聯絡。 此資訊儲存在「即時客戶個人檔案」資料庫中。 **技術使用者**&#x200B;需要設定Adobe Experience Platform資料來源以擷取這些欄位。

如需資料來源組態的詳細資訊，請參閱[此頁面](../datasource/about-data-sources.md)。

1. 在功能表窗格中，選取&#x200B;**[!UICONTROL Admin]**。 在&#x200B;**[!UICONTROL Data sources]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Manage]**。
1. 選取內建的Adobe Experience Platform資料來源。

   ![](../assets/journey23.png)

1. 在預先設定的群組欄位中，檢查是否已選取下列欄位：

   * _人員>姓名>名字_
   * _人員>姓名>姓氏_
   * _個人電子郵件>地址_

1. 按一下「**[!UICONTROL Add a New Field Group]**」，選取&#x200B;**[!UICONTROL Profiles]**&#x200B;結構描述，並新增條件的&#x200B;**忠誠度會員**&#x200B;欄位。 **忠誠度會員**&#x200B;欄位是自訂欄位，已在XDM中新增：「_customer > marlton > loyaltyMember」

   ![](../assets/journeyuc2_6.png)

1. 按一下&#x200B;**[!UICONTROL Add a New Field Group]**，選取&#x200B;**[!UICONTROL ExperienceEvent]**&#x200B;結構描述，並針對指定期間內傳送的訊息數目，選擇條件所需的欄位：日期為&#x200B;_時間戳記_，傳送的訊息數目為&#x200B;_directMarketing >傳送>值_。

   ![](../assets/journeyuc2_7.png)

1. 按一下「**[!UICONTROL Save]**」。

我們還需要檢查客人在飯店訂房系統中是否有預訂。 **技術使用者**&#x200B;需要設定第二個資料來源以擷取此欄位。

1. 在資料來源清單中，按一下&#x200B;**[!UICONTROL Add]**&#x200B;以新增外部資料來源，以定義與您的飯店訂房系統的連線。

   ![](../assets/journeyuc2_9.png)

1. 輸入您的資料來源名稱及外部服務的URL，例如： _https://marlton.com/reservation_

   >[!CAUTION]
   >
   >基於安全考量，我們強烈建議使用HTTPS。

1. 根據外部服務配置設定身份驗證：**[!UICONTROL No authentication]**、**[!UICONTROL Basic]**、**[!UICONTROL Custom]** 或 **[!UICONTROL API key]**。在我們的範例中，我們為型別選擇「基本」，並指定API呼叫的使用者名稱和密碼。

   ![](../assets/journeyuc2_10.png)

1. 按一下&#x200B;**[!UICONTROL Add a New Field Group]**&#x200B;以定義要擷取的資訊和API引數。 在我們的範例中，只有一個引數(ID)，因此我們需要建立一個包含下列資訊的欄位群組：

   * **[!UICONTROL Method]**：選取 POST 或 GET 方法。在本例中，我們選取 GET 方法。
   * **[!UICONTROL Response Payload]**：在&#x200B;**[!UICONTROL Payload]**&#x200B;欄位內按一下，並貼上裝載的範例。 確認欄位類型是否正確。每次呼叫 API 時，系統都會擷取有效負載範例中包含的所有欄位。在我們的範例中，裝載僅包含預訂狀態：

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamic Values]**：輸入與用來識別每位客戶的金鑰對應的引數，範例中為「id」。 此引數的值將在歷程中定義。

   ![](../assets/journeyuc2_11.png)

1. 按一下「**[!UICONTROL Save]**」。

   資料來源現在已設定完畢，且可供您在歷程中使用。
