---
product: adobe campaign
title: 區段資格事件
description: 了解區段資格事件
feature: Journeys
role: User
level: Intermediate
exl-id: e8e54dbd-8178-4c70-907c-68eb4dc54da7
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 1%

---

# 區段資格事件 {#segment-qualification}

## 關於區段資格事件{#about-segment-qualification}

此活動可讓您的歷程監聽Adobe Experience Platform區段中設定檔的入口和出口，以便讓個人進入歷程或在歷程中前進。 如需區段建立的詳細資訊，請參閱 [節](../segment/about-segments.md).

假設您有「銀色客戶」區段。 透過此活動，您可以讓所有新銀級客戶進入歷程，並傳送一系列個人化訊息。

這類事件可定位為歷程的第一步或稍後步驟。

>[!IMPORTANT]
>
>請記住，Adobe Experience Platform區段每天計算一次(**批次** 區段)或即時(**流式** 區段，使用Adobe Experience Platform的「高頻率對象」選項。
>
>如果將選取的區段串流化，屬於此區段的個人可能會即時進入歷程。 如果區段為批次，新符合此區段資格的人員可能會在Adobe Experience Platform上執行區段計算時進入歷程。


1. 展開 **[!UICONTROL Events]** 類別和拖放 **[!UICONTROL Segment qualification]** 活動進入您的畫布。

   ![](../assets/segment5.png)

1. 新增 **[!UICONTROL Label]** 至活動。 此步驟為選填。

1. 按一下 **[!UICONTROL Segment]** 欄位，並選取您要運用的區段。

   >[!NOTE]
   >
   >請注意，您可以自訂清單中顯示的欄，並加以排序。

   ![](../assets/segment6.png)

   新增區段後， **[!UICONTROL Copy]** 按鈕可讓您複製其名稱和ID:

   `{"name":"Loyalty membership“,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-copy.png)

1. 在 **[!UICONTROL Behaviour]** 欄位，選擇您要監聽區段入口、出口還是兩者。

   >[!NOTE]
   >
   >請注意 **[!UICONTROL Enter]** 和 **[!UICONTROL Exit]** 對應至 **已實現** 和 **退出** 來自Adobe Experience Platform的區段參與狀態。 如需如何評估區段的詳細資訊，請參閱 [區段服務檔案](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

1. 選取命名空間。 唯有將事件定位為歷程的第一步時，才需要此選項。

   ![](../assets/segment7.png)

裝載包含下列內容資訊，您可在條件和動作中使用：

* 行為（入口、出口）
* 資格時間戳記
* 區段id

在遵循的條件或動作中使用運算式編輯器時 **[!UICONTROL Segment qualification]** 活動，您可以存取 **[!UICONTROL SegmentQualification]** 節點。 您可以選擇 **[!UICONTROL Last qualification time]** 和 **[!UICONTROL status]** （輸入或退出）。

請參閱 [條件活動](../building-journeys/condition-activity.md#about_condition).

![](../assets/segment8.png)

包含區段資格事件的新歷程會在您發佈後10分鐘內運作。 此時間間隔對應於專用服務的快取刷新間隔。 因此，您必須等待10分鐘才能使用此歷程。

## 最佳做法 {#best-practices-segments}

此 **[!UICONTROL Segment Qualification]** 活動可讓從Adobe Experience Platform區段中取得資格或取消資格之個人的歷程立即進入。

這種資訊的接收速度很快。 進行的測量顯示每秒收到10,000個事件的速度。 因此，你應該確保你明白，如何達到入口高峰，如何避開它們，以及如何為它們做好準備。

### 批次區段{#batch-speed-segment-qualification}

對批段使用段資格時，請注意，在每日計算時將出現入口峰值。 峰值的大小取決於每天進入（或退出）區段的個人人數。

此外，如果批次區段是新建立的，且立即用於歷程中，第一批計算可能會讓大量個人進入歷程。

### 串流區段{#streamed-speed-segment-qualification}

對串流區段使用區段資格時，由於持續評估區段，導致入口/出口處出現大峰值的風險較低。 不過，如果區段定義導致大量客戶同時符合資格，則可能也會出現峰值。

如需串流細分的詳細資訊，請參閱 [頁面](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/streaming-segmentation.html#api)

### 如何避免過載{#overloads-speed-segment-qualification}

以下是一些最佳實務，可協助避免歷程中運用的系統超載(資料來源、自訂動作、Adobe Campaign Standard動作)。

請勿在 **[!UICONTROL Segment Qualification]** 活動，即建立後立即批次區段。 它將避免第一個計算峰值。 請注意，如果您要使用從未計算過的區段，歷程畫布中會出現黃色警告。

![](../assets/segment-error.png)

為歷程中使用的資料來源和動作設定上限規則，以避免超出負載(請參閱此 [節](../api/capping.md))。 請注意，上限規則沒有重試。 如果您需要重試，您必須核取方塊，以在歷程中使用替代路徑 **[!UICONTROL Add an alternative path in case of a timeout or an error]** 在條件或動作中。

在生產歷程中使用區段之前，請務必先評估每天符合此區段資格的個人數量。 若要這麼做，您可以檢查 **[!UICONTROL Segments]** 區段，並查看右側的圖形。

![](../assets/segment-overload.png)
