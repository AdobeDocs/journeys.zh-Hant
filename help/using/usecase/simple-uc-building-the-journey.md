---
product: adobe campaign
title: 構建旅程 — 簡單
description: 瞭解如何構建簡單的使用案例之旅
feature: Journeys
role: User
level: Intermediate
exl-id: 22bcd7f4-03ee-4e4c-b221-9f14aeadded6
source-git-commit: 9db330405130b14d1d8a8cbed59f612fd1f6767b
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 35%

---

# 建立歷程{#concept_eyw_mcy_w2b}

**商業使用者**&#x200B;現在可以建立歷程。我們的旅程將只包括一條路徑，其中包括以下活動：

* &quot;水療信標&quot; **[!UICONTROL Event]**:當一個人走近spa信標時，系統會收到一個活動，而這個人的旅程將開始。
* a **[!UICONTROL Condition]** 檢查此人是否為女性
* 一個 **[!UICONTROL Email]** 活動(使用Adobe Campaign Standard)
* 一個 **[!UICONTROL End]** 活動

>[!NOTE]
>
>只有當您具有 Adobe Campaign Standard　時，浮動視窗才能使用　**[!UICONTROL Push]**　及 **[!UICONTROL Email]**　活動。

有關如何構建行程的其他資訊，請參閱 [此頁](../building-journeys/journey.md)。

1. 在頂端功能表中，按一下 **[!UICONTROL Home]** 索引標籤及 **[!UICONTROL Create]**，以建立新的歷程。

   ![](../assets/journey31.png)

1. 在右側顯示的設定窗格中，編輯歷程的屬性。我們把它命名為&quot;Spa之旅&quot;，並設定為12月1日至31日持續一個月。

   ![](../assets/journeyuc1_8.png)

1. 通過將「SpaBeacon」事件從調色板拖放到畫布，開始設計您的旅程。 您也可以連按兩下浮動視窗中的事件，將之新增至畫布。

   ![](../assets/journeyuc1_9.png)

1. 現在，我們添加一個條件來檢查此人是否是女性。 將條件活動拖放至歷程中。

   ![](../assets/journeyuc1_10.png)

1. 選擇 **[!UICONTROL Data Source Condition]** 類型，然後按一下 **[!UICONTROL Expression]** 欄位。您也可以定義條件標籤，該標籤將顯示在畫布的箭頭上。

   ![](../assets/journeyuc1_11.png)

1. 使用簡單的表達式編輯器查找性別欄位(_人員>性別_)並將其右移以建立以下條件：&quot;性別等於&quot;女性&quot;。

   ![](../assets/journeyuc1_12.png)

1. 刪除 **[!UICONTROL Email]** 活動並選擇「Spa折扣」事務性消息傳遞模板。 此模板是使用Adobe Campaign設計的。 請參閱此 [頁](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=zh-Hant)。

   ![](../assets/journeyuc1_13.png)

1. 在 **[!UICONTROL Email]** 欄位，然後從資料源中選擇電子郵件地址。

   ![](../assets/journeyuc1_14.png)

1. 同樣，從資料源定義名和姓個性化欄位。

   ![](../assets/journeyuc1_15.png)

1. 刪除 **[!UICONTROL End]** 的子菜單。

   ![](../assets/journeyuc1_17.png)

1. 按一下 **[!UICONTROL Test]** 使用test配置檔案切換和test行程。 如果發生任何錯誤，請停用測試模式、修改您的歷程並再次測試。有關test模式的詳細資訊，請參閱 [此頁](../building-journeys/testing-the-journey.md)。

   ![](../assets/journeyuc1_18bis.png)

1. 當測試結果確定時，您可以從右上角的下拉式功能表發佈您的歷程。

   ![](../assets/journeyuc1_18.png)

下次，當一位女性走近Spa信標時，她會立即收到一封「Spa折扣」個性化電子郵件。
