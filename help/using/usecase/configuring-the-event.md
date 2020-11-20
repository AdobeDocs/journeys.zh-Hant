---
product: adobe campaign
solution: Journey Orchestration
title: 設定事件
description: 瞭解如何針對歷程中的簡單使用案例設定活動
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 8%

---


# 設定事件{#concept_y44_hcy_w2b}

在我們的場景中，每當一個人走近位於spa旁的信標時，就需要收到一個活動。 技 **術使用者** ，需要設定系統在歷程中將監聽的事件。

有關事件配置的其他資訊，請參 [閱此頁](../event/about-events.md)。

1. In the top menu, click the **[!UICONTROL Events]** tab and click **[!UICONTROL Add]** to create a new event.

   ![](../assets/journeyuc1_1.png)

1. 我們輸入不含空格或特殊字元的名稱：&quot;SpaBeacon&quot;。

   ![](../assets/journeyuc1_2.png)

1. 接著，我們選取架構並定義此事件預期的裝載。 從XDM標準化模型中選取所需欄位。 我們需要Experience Cloud ID來識別即時客戶個人檔案資料庫中的人員： _endUserIDs >體驗> mcid > id_。 系統會自動為此事件產生ID。 此ID會儲存在欄位 **[!UICONTROL eventID]** 中(_體驗>促銷活動>協調> eventID_)。 推送事件的系統不應產生ID，而應使用裝載預覽中可用的ID。 在我們的使用案例中，此ID用於識別信標位置。 每次有人走近Spa信標時，就會傳送包含此特定事件ID的事件。 這可讓系統知道觸發事件傳送的信標。

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >欄位清單會依不同的架構而有所不同。 根據架構定義，某些欄位可能是必填和預選的。

1. 我們需要選擇一個命名空間。根據架構屬性，預先選取命名空間。您可以將命名空間保持預選狀態。For more information on namespaces, see [this page](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc1_6.png)

1. 基於模式屬性和選擇的命名空間預選鍵。 你留著吧。

   ![](../assets/journeyuc1_5.png)

1. 按一下 **[!UICONTROL Save]**。

1. 按一下 **[!UICONTROL View Payload]** 圖示可預覽系統預期的裝載，並與負責事件傳送的人員共用。 此裝載必須在Mobile Services管理控制台的回傳中設定。

   ![](../assets/journeyuc1_7.png)

   該活動已準備好供您的旅程使用。 您現在需要設定行動應用程式，以便將預期的負載傳送至串流擷取API端點。 請參閱[本頁](../event/additional-steps-to-send-events-to-journey-orchestration.md)。