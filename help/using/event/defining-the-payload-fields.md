---
title: 定義裝載欄位
description: 瞭解如何定義裝載欄位
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: e353d593ab2710f50a88a3715378c86c2e37b4f6
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 6%

---


# 定義裝載欄位 {#concept_yrw_3qt_52b}

有效負載定義可讓您選擇系統預期從歷程中的事件接收的資訊，以及識別與事件相關聯的人員的金鑰。 裝載是以Experience Cloud XDM欄位定義為基礎。 For more information on XDM, refer to [this page](https://docs.adobe.com/content/help/zh-Hant/experience-platform/xdm/home.html).

1. 從清單中選擇一個XDM方案，然後按一下 **[!UICONTROL Payload]** 欄位或表徵圖 **[!UICONTROL Edit]** 上。

   ![](../assets/journey8.png)

   將顯示架構中定義的所有欄位。 欄位清單會依不同的架構而有所不同。 您可以搜尋特定欄位，或使用篩選器來顯示所有節點和欄位，或僅顯示選取的欄位。 根據架構定義，某些欄位可能是必填和預選的。 您無法取消選取它們。

   >[!NOTE]
   >
   >請確定您已將「協調」混合加入XDM架構。 這將確保您的架構包含所有需要使用的資訊 [!DNL Journey Orchestration]。

   ![](../assets/journey9.png)

1. 選擇您希望從事件接收的欄位。 這些是商業使用者在歷程中將運用的欄位。 它們也必須包含用來識別與事件相關聯之人員的金鑰(請參 [閱本頁](../event/defining-the-event-key.md))。

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >欄位 **[!UICONTROL eventID]** 會自動新增至選取欄位清單中，以便 [!DNL Journey Orchestration] 識別事件。 推送事件的系統不應產生ID，而應使用裝載預覽中可用的ID。 請參閱[本頁](../event/previewing-the-payload.md)。

1. 選擇完所需欄位後，按一下或 **[!UICONTROL Save]** 按 **[!UICONTROL Enter]**。

   ![](../assets/journey11.png)

   選取的欄位數會顯示在欄位 **[!UICONTROL Payload]** 中。

   ![](../assets/journey12.png)
