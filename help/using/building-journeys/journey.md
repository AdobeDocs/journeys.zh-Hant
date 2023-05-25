---
product: adobe campaign
title: 關於建立歷程
description: 身為企業使用者，了解如何結合活動、協調和行銷活動，以構建歷程。
feature: Journeys
role: User
level: Intermediate
exl-id: 540b5142-9323-4cc1-9b5a-3fa20a5945bf
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 21%

---

# 建立歷程 {#concept_gq5_sqt_52b}

此步驟由執行 **業務使用者**. 這是您建立歷程的位置。 結合不同的事件、協調和動作活動，以建立您的多步驟跨管道情境。

歷程介面可讓您輕鬆地將活動從調色盤拖放到畫布中。您還可以按兩下活動以在下一步可用時將其新增到畫布中。每個活動在流&#39;b5&#39;7b中具有特定的角色和位置。 活動會進行序列化。 活動完成後，流程會繼續並處理下一個活動，依此類推。

每個歷程只允許一個名稱空間。 當您拖放第一個事件時，具有不同名稱空間的事件將會呈現灰色。 如果第一個事件沒有名稱空間，則具有名稱空間的所有事件都將變成灰色。 請參閱[此頁面](../event/selecting-the-namespace.md)。此外，如果歷程具有沒有名稱空間的事件，Adobe Experience Platform欄位群組會呈現灰色。 最後，如果您在同一個歷程中使用數個事件，則它們需要使用相同的名稱空間。

開始新歷程時，無法在第一步驟放入畫布的元素會隱藏。 這關係到所有動作、狀況活動、等待和反應。

## 快速入門 {#creating_journey}

以下是建立和發佈歷程的主要步驟。

1. 在頂端功能表中，按一下 **[!UICONTROL Home]** 索引標籤。

   隨即顯示歷程清單。 請參閱 [此頁面](../building-journeys/using-the-journey-designer.md) 以取得介面的詳細資訊。

   ![](../assets/journey30.png)

1. 按一下 **[!UICONTROL Create]** 以建立新歷程。

   ![](../assets/journey31.png)

1. 在右側顯示的設定窗格中，編輯歷程的屬性。請參閱[此頁面](../building-journeys/changing-properties.md)。

   ![](../assets/journey32.png)

1. 首先，將事件活動從浮動視窗拖放至畫布中。 您也可以連按兩下活動，將其新增至畫布。

   ![](../assets/journey33.png)

1. 拖放其他活動並進行設定。 請參閱頁面 [事件活動](../building-journeys/event-activities.md)， [關於協調活動](../building-journeys/about-orchestration-activities.md) 和 [關於動作活動](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. 您的歷程會自動儲存。 測試您的歷程並發佈。 另請參閱 [測試歷程](../building-journeys/testing-the-journey.md) 和 [發佈歷程](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## 結束歷程 {#ending_a_journey}

歷程可以因個人原因結束：

* 該人員到達路徑的最後一個活動。 此最後一個活動可以是結束活動或其他活動。 沒有義務以結束活動來結束路徑。 請參閱[此頁面](../building-journeys/end-activity.md)。
* 該人員到達條件活動（或具有條件的等待活動），但不符合任何條件。

如果允許重新進入，則人員可以重新進入歷程。 請參閱[此頁面](../building-journeys/changing-properties.md)。

歷程可以關閉，原因如下：

* 已透過手動關閉歷程 **[!UICONTROL Close to new entrances]** 按鈕。
* 已達到歷程的結束日期。

當歷程關閉時（基於上述任何原因），它將具有狀態 **[!UICONTROL Closed]**. 歷程將停止讓新個人進入歷程。 已在歷程中的人員將正常完成歷程。 在預設全域逾時30天後，歷程將切換為 **已完成** 狀態。 請參閱[本章節](../building-journeys/changing-properties.md#entrance)。

如果您需要停止歷程中所有個人的進度，您可以停止它。 停止歷程將會讓歷程中的所有個人逾時。

若要瞭解如何手動關閉或停止歷程，請參閱此 [區段](../building-journeys/terminating-a-journey.md).
