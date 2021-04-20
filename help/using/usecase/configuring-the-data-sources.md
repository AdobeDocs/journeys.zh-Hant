---
product: adobe campaign
solution: Journey Orchestration
title: 設定資料來源
description: 瞭解如何為歷程進階使用案例設定資料來源
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 14%

---


# 設定資料來源 {#concept_vml_hdy_w2b}

在我們的使用案例中，我們想要將個人化資料用於我們的訊息。 我們還需要檢查此人是否是忠誠會員，且在過去24小時內未與他聯繫。 此資訊會儲存在即時客戶個人檔案資料庫中。 **技術用戶**&#x200B;需要配置Adobe Experience Platform資料源以檢索這些欄位。

有關資料源配置的其他資訊，請參閱[本頁](../datasource/about-data-sources.md)。

1. 在頂部菜單中，按一下&#x200B;**[!UICONTROL Data Sources]**&#x200B;頁籤並選擇內置的Adobe Experience Platform資料源。

   ![](../assets/journey23.png)

1. 在預先設定的群組欄位中，檢查下列欄位是否已選取：

   * _person > name > firstName_
   * _person > name > lastName_
   * _個人電子郵件>地址_

1. 按一下&#x200B;**[!UICONTROL Add a New Field Group]**，選擇&#x200B;**[!UICONTROL Profiles]**&#x200B;方案，並為我們的條件添加&#x200B;**Loyalty member**&#x200B;欄位。 **Loyalty member**&#x200B;欄位是自訂欄位，已新增至XDM:&quot;_customer > marlton > loyaltyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. 按一下&#x200B;**[!UICONTROL Add a New Field Group]** ，選擇&#x200B;**[!UICONTROL ExperienceEvent]**&#x200B;方案，並選擇條件所需的欄位，以瞭解在指定期間發送的消息數：_timestamp_&#x200B;表示日期，_directMarketing >傳送> value_&#x200B;表示傳送的訊息數。

   ![](../assets/journeyuc2_7.png)

1. 按一下 **[!UICONTROL Save]**。

我們還需要檢查該人是否在飯店訂房系統中有訂房。 **技術使用者**&#x200B;需要設定第二個資料來源以擷取此欄位。

1. 在資料來源清單中，按一下&#x200B;**[!UICONTROL Add]**&#x200B;以新增外部資料來源，以定義與酒店訂房系統的連線。

   ![](../assets/journeyuc2_9.png)

1. 輸入資料來源的名稱和外部服務的URL，例如：_https://marlton.com/reservation_

   >[!CAUTION]
   >
   >基於安全考量，我們強烈建議您使用 HTTPS。

1. 根據外部服務配置設定身份驗證：**[!UICONTROL No authentication]**、**[!UICONTROL Basic]**、**[!UICONTROL Custom]** 或 **[!UICONTROL API key]**。在我們的範例中，我們為類型選擇「基本」，並指定API呼叫的使用者名稱和密碼。

   ![](../assets/journeyuc2_10.png)

1. 按一下&#x200B;**[!UICONTROL Add a New Field Group]**&#x200B;定義要檢索的資訊和API參數。 在我們的範例中，只有一個參數(id)，因此我們需要建立一個包含下列資訊的欄位群組：

   * **[!UICONTROL Method]**：選取 POST 或 GET 方法。在本例中，我們選取 GET 方法。
   * **[!UICONTROL Cache duration]**:這視API呼叫的頻率而定。在我們的情況下，訂房系統每10分鐘更新一次。
   * **[!UICONTROL Response Payload]**:在欄位內 **[!UICONTROL Payload]** 按一下，然後貼上裝載範例。確認欄位類型是否正確。每次呼叫 API 時，系統都會擷取有效負載範例中包含的所有欄位。在我們的範例中，裝載只包含保留狀態：

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamic Values]**:在我們的範例中輸入與用來識別每個客戶的索引鍵相對應的參數「id」。此參數的值將定義在歷程中。

   ![](../assets/journeyuc2_11.png)

1. 按一下 **[!UICONTROL Save]**。

   資料來源現在已經設定好，可供您在歷程中使用。
