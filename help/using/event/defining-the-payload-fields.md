---
product: adobe campaign
title: 定義裝載欄位
description: 瞭解如何定義裝載欄位
feature: Journeys
role: User
level: Intermediate
exl-id: 9d385b64-46cd-489b-9c18-352fa2a2dbba
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 3%

---

# 定義裝載欄位 {#concept_yrw_3qt_52b}



>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_


裝載定義可讓您選擇系統預期從歷程中的事件接收的資訊，以及識別與事件相關聯之人員的金鑰。 裝載是根據Experience Cloud XDM欄位定義。 如需XDM的詳細資訊，請參閱[此頁面](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hant)。

1. 從清單中選取XDM結構描述，然後按一下「**[!UICONTROL Payload]**」欄位或「**[!UICONTROL Edit]**」圖示。

   ![](../assets/journey8.png)

   結構描述中定義的所有欄位都會顯示。 欄位清單會因結構描述而異。 您可以搜尋特定欄位，或使用篩選器來顯示所有節點和欄位，或僅顯示選定的欄位。 根據結構描述定義，某些欄位可能是必填欄位並預先選取。 您無法取消選取它們。 依預設，系統會選取Journey Orchestration正確接收事件所必須的所有欄位。

   >[!NOTE]
   >
   >請確定您已將「協調流程」mixin新增至XDM結構描述。 這將確保您的結構描述包含使用[!DNL Journey Orchestration]所需的所有資訊。

   ![](../assets/journey9.png)

1. 選取您預期會從事件接收的欄位。 這些是業務使用者將在歷程中善用的欄位。 它們也必須包含用來識別與事件相關聯之人員的金鑰（請參閱[此頁面](../event/defining-the-event-key.md)）。

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >對於系統產生的事件，**[!UICONTROL eventID]**&#x200B;欄位會自動新增到選取的欄位清單中，以便[!DNL Journey Orchestration]可以識別事件。 推播事件的系統不應產生ID，而應使用裝載預覽中可用的ID。 請參閱[此頁面](../event/previewing-the-payload.md)。

1. 選取完所需的欄位後，按一下&#x200B;**[!UICONTROL Save]**&#x200B;或按&#x200B;**[!UICONTROL Enter]**。

   ![](../assets/journey11.png)

   所選欄位的數量會出現在&#x200B;**[!UICONTROL Payload]**&#x200B;欄位中。

   ![](../assets/journey12.png)
