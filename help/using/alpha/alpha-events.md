---
title: 規則型事件
description: 進一步瞭解規則型事件。
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f146a22cec5ffbbc61b51f8fc3c875078b2ee6bf
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 4%

---


# 規則型事件{#simplified-events}

我們已簡化您設定「體驗」活動的方式。 我們將推出不需要使用eventID的新方法。 當您在「歷程協調」中設定活動時，現在可以定義規則型活動。

這種新類型的事件不會產生eventID。 使用簡單運算式編輯器，您現在只需定義規則，系統將使用該規則來識別將觸發您歷程的相關事件。 此規則可以根據事件裝載中可用的任何欄位，例如描述檔位置或新增至描述檔購物車的項目數。

這種新方法對用戶來說大多是透明的。 唯一的變更是事件定義畫面中的新欄位。

1. 在左側功能表中，按一下「管 **理員** 」圖示，然後按一 **下「事件」**。 畫面隨即顯示事件清單。

   ![](../assets/alpha-event1.png)

1. Click **Add** to create a new event. 事件設定窗格會在畫面右側開啟。

   ![](../assets/alpha-event2.png)

1. 輸入事件的名稱。 您也可以新增說明。

   ![](../assets/alpha-event3.png)

1. 在新的「事 **件ID類型** 」欄位中，選 **取「規則型」**。

   ![](../assets/alpha-event4.png)

   >[!NOTE]
   >
   >「 **系統產生** 」類型是需要eventID的現有方法。 請參 [閱本節](../event/about-events.md)。

1. 定義方 **案** 和裝載 **欄位**。 請參 [閱本節](../event/defining-the-payload-fields.md)。

   ![](../assets/alpha-event5.png)

   >[!NOTE]
   >
   >選擇「系統生 **成」類型時**，只有具有eventID類型混合的方案可用。 當您選取「規則 **型」類型** 時，所有「體驗事件」結構都可用。

1. 在「事件 **ID條件」欄位內按一下** 。 使用簡單運算式編輯器，定義系統將用來識別將觸發您旅程的事件的條件。

   ![](../assets/alpha-event6.png)

   在我們的例子中，我們根據個人檔案的城市寫了一個條件。 這表示每當系統收到符合此條件(**City** field和 **Paris** value)的事件時，就會將它傳送至Journey Orchestration。

1. 定義 **Namespace** 和 **Key**。 請參 [閱選擇命名空間](../event/selecting-the-namespace.md)[和定義事件鍵](../event/defining-the-event-key.md)。

   ![](../assets/alpha-event7.png)

事件設定和歷程建立的其他步驟保持不變。

現在，該事件已設定好，並可像其他任何事件一樣拖放至歷程中。 每次將符合規則的事件傳送至系統時，就會傳送至Journey Orchestration以觸發您的歷程。

