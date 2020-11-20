---
product: adobe campaign
solution: Journey Orchestration
title: 設定事件
description: 瞭解如何為歷程進階使用案例設定事件
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 7%

---


# 設定事件 {#concept_sbp_5cy_w2b}

在我們的情形中，每次有人進入馬爾頓酒店和餐廳時，我們都需要得到一個活動。 技 **術使用者** ，需要設定我們希望系統在歷程中聆聽的兩個事件。

有關事件配置的其他資訊，請參 [閱此頁](../event/about-events.md)。

1. In the top menu, click the **[!UICONTROL Events]** tab and click **[!UICONTROL Add]** to create a new event.

   ![](../assets/journeyuc1_1.png)

1. 我們輸入的名稱沒有空格或特殊字元：&quot;LobbyBeacon&quot;。

   ![](../assets/journeyuc2_1.png)

1. 接著，我們選取架構並定義此事件預期的裝載。 從XDM標準化模型中選取所需欄位。 我們需要Experience Cloud ID來識別即時客戶個人檔案資料庫中的人員：&quot;endUserIDs > _experience > mcid > id&quot;。

   我們還需要註冊Token來傳送推播訊息：&quot;_experience >促銷活動>訊息>描述檔>推播通知Token > Token&quot;

   系統會自動為此事件產生ID。 此ID會儲存在欄 **[!UICONTROL eventID]** 位（&quot;_experience >促銷活動>協調>eventID&quot;）中。 推送事件的系統不應產生ID，而應使用裝載預覽中可用的ID。 在我們的使用案例中，此ID用於識別信標位置。 每當訪客在大堂信標附近散步時，就會傳送包含此特定事件ID的事件。 同樣的原則也適用於餐廳信標事件。 這可讓系統知道觸發事件傳送的信標。

   ![](../assets/journeyuc2_2.png)

   >[!NOTE]
   >
   >欄位清單會依不同的架構而有所不同。 根據架構定義，某些欄位可能是必填和預選的。

1. 我們需要選擇一個命名空間。根據架構屬性，預先選取命名空間。您可以將命名空間保持預選狀態。For more information on namespaces, see [this page](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc2_4.png)

1. 基於模式屬性和選擇的命名空間預選鍵。 你留著吧。

   ![](../assets/journeyuc2_4bis.png)

1. 按一下 **[!UICONTROL Save]**。

1. 按一下 **[!UICONTROL View Payload]** 圖示可預覽系統預期的裝載，並與負責事件傳送的人員共用。  此裝載必須在Mobile Services管理控制台的回傳中設定。

   ![](../assets/journeyuc2_5.png)

同樣地，請建立「RestaurantBeacon」事件。 您建立了兩個信標事件，現在可用於我們的歷程。 您現在需要設定行動應用程式，以便將預期的負載傳送至串流擷取API端點。 請參閱[本頁](../event/additional-steps-to-send-events-to-journey-orchestration.md)。
