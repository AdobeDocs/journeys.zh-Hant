---
product: adobe campaign
title: 建立歷程
description: 了解如何建立簡單的使用案例歷程
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 22bcd7f4-03ee-4e4c-b221-9f14aeadded6
source-git-commit: 3af822bacfd1a5a53ec7280dff1136d77b90c809
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 34%

---

# 建立歷程{#concept_eyw_mcy_w2b}

**商業使用者**&#x200B;現在可以建立歷程。我們的歷程將僅包含一個路徑，其中包含下列活動：

* &quot;SpaBeacon&quot; **[!UICONTROL Event]**:當使用者在spa信標附近散步時，系統會收到一個事件，而該使用者的歷程就會開始。
* **[!UICONTROL Condition]**&#x200B;活動，以檢查該人是否為女性
* **[!UICONTROL Email]**&#x200B;活動(使用Adobe Campaign Standard)
* **[!UICONTROL End]**&#x200B;活動

>[!NOTE]
>
>只有當您具有 Adobe Campaign Standard　時，浮動視窗才能使用　**[!UICONTROL Push]**　及 **[!UICONTROL Email]**　活動。

如需如何建立歷程的詳細資訊，請參閱[本頁面](../building-journeys/journey.md)。

1. 在頂端功能表中，按一下 **[!UICONTROL Home]** 索引標籤及 **[!UICONTROL Create]**，以建立新的歷程。

   ![](../assets/journey31.png)

1. 在右側顯示的設定窗格中，編輯歷程的屬性。我們將其命名為「Spa歷程」，並設為持續一個月，從12月1日到31日。

   ![](../assets/journeyuc1_8.png)

1. 從浮動視窗拖放「SpaBeacon」事件至畫布，開始設計您的歷程。 您也可以連按兩下浮動視窗中的事件，將之新增至畫布。

   ![](../assets/journeyuc1_9.png)

1. 現在來新增條件，以檢查該人是否為女性。 將條件活動拖放至歷程中。

   ![](../assets/journeyuc1_10.png)

1. 選擇 **[!UICONTROL Data Source Condition]** 類型，然後按一下 **[!UICONTROL Expression]** 欄位。您也可以定義條件標籤，該標籤將顯示在畫布的箭頭上。

   ![](../assets/journeyuc1_11.png)

1. 使用簡單運算式編輯器，尋找性別欄位(_person > gender_)，並將其拖曳至右側，以建立下列條件：&quot;性別等於&quot;女性&quot;。

   ![](../assets/journeyuc1_12.png)

1. 拖放&#x200B;**[!UICONTROL Email]**&#x200B;活動，並選取「Spa折扣」交易式訊息範本。 此範本是使用Adobe Campaign設計。 請參閱此[page](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html)。

   ![](../assets/journeyuc1_13.png)

1. 按一下&#x200B;**[!UICONTROL Email]**&#x200B;欄位內的，然後從資料來源選取電子郵件地址。

   ![](../assets/journeyuc1_14.png)

1. 同樣地，從資料來源定義名字和姓氏個人化欄位。

   ![](../assets/journeyuc1_15.png)

1. 刪除&#x200B;**[!UICONTROL End]**&#x200B;活動。

   ![](../assets/journeyuc1_17.png)

1. 按一下&#x200B;**[!UICONTROL Test]**&#x200B;切換並使用測試設定檔測試您的歷程。 如果發生任何錯誤，請停用測試模式、修改您的歷程並再次測試。有關測試模式的詳細資訊，請參閱[此頁](../building-journeys/testing-the-journey.md)。

   ![](../assets/journeyuc1_18bis.png)

1. 當測試結果確定時，您可以從右上角的下拉式功能表發佈您的歷程。

   ![](../assets/journeyuc1_18.png)

下次當女性在Spa信標附近散步時，她會立即收到「Spa折扣」個人化電子郵件。
