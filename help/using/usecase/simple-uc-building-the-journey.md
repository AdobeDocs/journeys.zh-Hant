---
title: 打造旅程
description: 瞭解如何建立簡單的使用案例歷程
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# 打造旅程{#concept_eyw_mcy_w2b}

商 **業使用者** ，現在可以建立歷程。 我們的旅程將僅包含一條路徑，其中包含下列活動：

* &quot;SpaBeacon&quot; **[!UICONTROL Event]**:當一個人走在水療信標附近時，系統會收到一個活動，而旅程將開始。
* 檢 **[!UICONTROL Condition]**查此人是否為女性的活動
* 活 **[!UICONTROL Email]**動（使用Adobe Campaign Standard）
* 活 **[!UICONTROL End]**動

>[!NOTE]
>
>只有在 **[!UICONTROL Push]**您有**[!UICONTROL Email]** Adobe Campaign Standard時，浮動視窗才能使用和活動。

如需如何建立歷程的詳細資訊，請參閱 [](../building-journeys/journey.md)。

1. 在頂端功能表中，按一下 **[!UICONTROL Home]**標籤並**[!UICONTROL Create]** 建立新的歷程。

   ![](../assets/journey31.png)

1. 在右側顯示的設定窗格中編輯歷程的屬性。 我們將它命名為&quot;Spa之旅&quot;，並設為持續一個月，從12月1日到31日。

   ![](../assets/journeyuc1_8.png)

1. 從浮動視窗拖放「SpaBeacon」事件至畫布，開始設計您的旅程。 您也可以連按兩下浮動視窗中的事件，將它新增至畫布。

   ![](../assets/journeyuc1_9.png)

1. 現在，我們添加一個條件來檢查此人是否是女性。 將條件活動拖放至您的歷程中。

   ![](../assets/journeyuc1_10.png)

1. 選擇類 **[!UICONTROL Data Source Condition]**型，然後在欄位中按一**[!UICONTROL Expression]** 下。 您也可以定義條件標籤，該標籤將顯示在畫布的箭頭上。

   ![](../assets/journeyuc1_11.png)

1. 使用簡單的運算式編輯器，尋找性別欄位(_person > geder_)，並將其拖曳至右側，以建立下列條件：&quot;性別等於&quot;女性&quot;。

   ![](../assets/journeyuc1_12.png)

1. 刪除活 **[!UICONTROL Email]**動並選擇「Spa折扣」交易訊息範本。 此範本是使用Adobe Campaign設計。 Refer to this[page](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

   ![](../assets/journeyuc1_13.png)

1. 在欄位內按 **[!UICONTROL Email]**一下，然後從資料來源選取電子郵件地址。

   ![](../assets/journeyuc1_14.png)

1. 同樣地，從資料來源定義名字和姓氏個人化欄位。

   ![](../assets/journeyuc1_15.png)

1. 刪除活 **[!UICONTROL End]**動。

   ![](../assets/journeyuc1_17.png)

1. 按一下切換 **[!UICONTROL Test]**並使用測試描述檔測試您的歷程。 如果有任何錯誤，請停用測試模式、修改您的歷程並再次測試。 有關測試模式的詳細資訊，請參閱[](../building-journeys/testing-the-journey.md)。

   ![](../assets/journeyuc1_18bis.png)

1. 當測試結果確定時，您可以從右上角的下拉式選單發佈您的旅程。

   ![](../assets/journeyuc1_18.png)

下次，當一名女性走近水療信標時，她會立即收到一封「Spa折扣」的個人化電子郵件。
