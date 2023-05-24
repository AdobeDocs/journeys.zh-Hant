---
product: adobe campaign
title: 設定事件
description: 瞭解如何為行程簡單使用案例配置事件
feature: Journeys
role: User
level: Intermediate
exl-id: 7423f4eb-005d-43a5-a403-97bee1e8d480
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 8%

---

# 設定事件{#concept_y44_hcy_w2b}

在我們的場景中，每當一個人走近位於spa旁的信標時，我們需要接收一個活動。 的 **技術用戶** 需要配置系統在我們的旅途中將收聽的事件。

有關事件配置的其他資訊，請參閱 [此頁](../event/about-events.md)。

1. 在頂部菜單中，按一下 **[!UICONTROL Events]** 頁籤 **[!UICONTROL Add]** 的子菜單。

   ![](../assets/journeyuc1_1.png)

1. 我們輸入不帶空格或特殊字元的名稱：&quot;SpaBeacon&quot;。

   ![](../assets/journeyuc1_2.png)

1. 然後，我們選擇該架構並定義此事件所需的負載。 從XDM歸一化模型中選取所需欄位。 我們需要Experience CloudID來標識即時客戶配置檔案資料庫中的人員： _endUserID >體驗> mcid > id_。 將自動為此事件生成ID。 此ID儲存在 **[!UICONTROL eventID]** 欄位(D)_體驗>市場活動>業務流程>事件ID_)。 推送事件的系統不應生成ID，它應使用負載預覽中可用的ID。 在我們的使用案例中，此ID用於標識信標位置。 每次人員在spa信標附近行走時，都會發送包含此特定事件ID的事件。 這樣，系統就可以知道觸發事件發送的信標。

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >欄位清單因方案而異。 根據架構定義，某些欄位可能是必需的並且預先選定。

1. 我們需要選擇一個命名空間。根據架構屬性，預先選取命名空間。您可以將命名空間保持預選狀態。有關命名空間的詳細資訊，請參見 [此頁](../event/selecting-the-namespace.md)。

   ![](../assets/journeyuc1_6.png)

1. 基於架構屬性和選定的命名空間預選鍵。 你可以留著。

   ![](../assets/journeyuc1_5.png)

1. 按一下「**[!UICONTROL Save]**」。

1. 按一下 **[!UICONTROL View Payload]** 表徵圖，預覽系統預期的負載，並將其與負責事件發送的人員共用。 需要在移動服務管理控制台的後退中配置此負載。

   ![](../assets/journeyuc1_7.png)

   該活動已準備好在您的旅途中使用。 現在，您需要配置移動應用程式，以便它能夠將預期的負載發送到流接收API端點。 請參閱[此頁面](../event/additional-steps-to-send-events-to-journey-orchestration.md)。
