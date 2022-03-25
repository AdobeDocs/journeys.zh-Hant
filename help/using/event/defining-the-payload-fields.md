---
product: adobe campaign
title: 定義裝載欄位
description: 瞭解如何定義負載欄位
feature: Journeys
role: User
level: Intermediate
exl-id: 9d385b64-46cd-489b-9c18-352fa2a2dbba
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 5%

---

# 定義裝載欄位 {#concept_yrw_3qt_52b}

有效負載定義允許您選擇系統希望從行程中的事件接收的資訊以及確定與事件關聯的人員的密鑰。 負載基於Experience CloudXDM欄位定義。 有關XDM的詳細資訊，請參閱 [此頁](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hant)。

1. 從清單中選擇XDM架構，然後按一下 **[!UICONTROL Payload]** 或 **[!UICONTROL Edit]** 表徵圖

   ![](../assets/journey8.png)

   將顯示架構中定義的所有欄位。 欄位清單因方案而異。 您可以搜索特定欄位，或使用篩選器顯示所有節點和欄位，或僅顯示選定欄位。 根據架構定義，某些欄位可能是必需的並且預先選定。 不能取消選擇它們。 預設情況下，Journey Orchestration正確接收事件所必需的所有欄位都將被選中。

   >[!NOTE]
   >
   >確保已將「業務流程」混合添加到XDM架構。 這將確保您的架構包含要使用的所有必需資訊 [!DNL Journey Orchestration]。

   ![](../assets/journey9.png)

1. 選擇要從事件接收的欄位。 這些是業務用戶在旅途中將利用的欄位。 它們還必須包括用於標識與事件關聯的人員的密鑰(請參閱 [此頁](../event/defining-the-event-key.md))。

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >對於系統生成的事件， **[!UICONTROL eventID]** 欄位將自動添加到選定欄位清單中，以便 [!DNL Journey Orchestration] 可以識別事件。 推送事件的系統不應生成ID，它應使用負載預覽中可用的ID。 請參閱[此頁面](../event/previewing-the-payload.md)。

1. 選擇完所需欄位後，按一下 **[!UICONTROL Save]** 按 **[!UICONTROL Enter]**。

   ![](../assets/journey11.png)

   所選欄位的數量顯示在 **[!UICONTROL Payload]** 的子菜單。

   ![](../assets/journey12.png)
