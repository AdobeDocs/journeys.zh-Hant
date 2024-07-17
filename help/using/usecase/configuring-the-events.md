---
product: adobe campaign
title: 設定事件
description: 瞭解如何設定歷程進階使用案例的事件
feature: Journeys
role: User
level: Intermediate
exl-id: 90139c72-8fae-4e6e-a79b-7c510f41fe38
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 7%

---

# 設定事件 {#concept_sbp_5cy_w2b}

在我們的案例中，每次有人進入瑪爾頓飯店和餐廳時，我們都需要收到一個事件。 **技術使用者**&#x200B;需要設定我們想要系統在歷程中接聽的兩個事件。

如需事件設定的詳細資訊，請參閱[此頁面](../event/about-events.md)。

1. 在頂端功能表中，按一下&#x200B;**[!UICONTROL Events]**&#x200B;索引標籤，然後按一下&#x200B;**[!UICONTROL Add]**&#x200B;以建立新事件。

   ![](../assets/journeyuc1_1.png)

1. 我們輸入的名稱不含空格或特殊字元：「LobbyBeacon」。

   ![](../assets/journeyuc2_1.png)

1. 接著，我們選取結構描述，並定義此事件預期的裝載。 我們從XDM標準化模型中選取所需的欄位。 我們需要Experience CloudID才能在即時客戶設定檔資料庫中識別人員：「endUserIDs > _experience > mcid > id」。

   我們還需要註冊Token才能傳送推送訊息：「_experience > campaign > message > profile > pushNotificationToken > token」

   系統會自動為此事件產生ID。 此ID儲存在&#x200B;**[!UICONTROL eventID]**&#x200B;欄位中(「_experience > campaign > orchestration > eventID」)。 推播事件的系統不應產生ID，而應使用裝載預覽中可用的ID。 在我們的使用案例中，此ID可用來識別信標位置。 每次有人靠近大廳信標時，系統都會傳送包含此特定事件ID的事件。 同一原則適用於餐廳信標事件。 這可讓系統知道哪些信標觸發了事件傳送。

   ![](../assets/journeyuc2_2.png)

   >[!NOTE]
   >
   >欄位清單會因結構描述而異。 根據結構描述定義，某些欄位可能是必填欄位並預先選取。

1. 我們需要選擇一個命名空間。根據架構屬性，預先選取命名空間。您可以將命名空間保持預選狀態。如需名稱空間的詳細資訊，請參閱[此頁面](../event/selecting-the-namespace.md)。

   ![](../assets/journeyuc2_4.png)

1. 系統會根據結構描述屬性及選取的名稱空間預先選取金鑰。 您可以保留它。

   ![](../assets/journeyuc2_4bis.png)

1. 按一下「**[!UICONTROL Save]**」。

1. 按一下&#x200B;**[!UICONTROL View Payload]**&#x200B;圖示可預覽系統預期的裝載，並與負責事件傳送的人員共用。  需要在Mobile Services管理主控台的回傳中設定此裝載。

   ![](../assets/journeyuc2_5.png)

同樣地，建立「RestaurantBeacon」事件。 您的兩個Beacon事件已建立，現在可用於我們的歷程。 您現在需要設定行動應用程式，才能將預期的裝載傳送至串流獲取API端點。 請參閱[此頁面](../event/additional-steps-to-send-events-to-journey-orchestration.md)。
