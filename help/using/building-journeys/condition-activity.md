---
product: adobe campaign
title: 條件活動
description: 了解條件活動
feature: 歷程
role: User
level: Intermediate
exl-id: 7b44edbe-9d05-4d67-8a64-2a0a553fcb92
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 10%

---

# 條件活動{#section_e2n_pft_dgb}

可用的條件有四種類型：

* [資料來源條件](#data_source_condition)
* [時間條件](#time_condition)
* [百分比分割](#percentage_split)
* [日期條件](#date_condition)

![](../assets/journey49.png)

## 關於條件活動 {#about_condition}

在歷程中使用數個條件時，您可以為每個條件定義標籤，以便更輕鬆地識別。

如果要定義多個條件，請按一下&#x200B;**[!UICONTROL Add a path]**。 對於每個條件，在活動之後的畫布中會新增路徑。

![](../assets/journey47.png)

請注意，歷程的設計會對功能造成影響。 在條件之後定義多個路徑時，只會執行第一個符合條件的路徑。 這表示您可以將路徑置於彼此上方或下方，以改變路徑的優先順序。

例如，我們以第一個路徑的條件「人是VIP」和第二個路徑的條件「人是男性」為例。 如果符合兩個條件的人(男性為VIP)通過此步驟，則即使他也符合第二個路徑的資格，也會選擇第一個路徑，因為第一個路徑「高於」。 若要變更此優先順序，請以另一個垂直順序移動活動。

![](../assets/journey48.png)

您可以勾選&#x200B;**[!UICONTROL Show path for other cases than the one(s) above]**，為不符合定義條件的對象建立其他路徑。 請注意，此選項不適用於分割條件。 請參閱[百分比分割](#percentage_split)。

簡單模式允許您根據欄位組合執行簡單查詢。 所有可用欄位都會顯示在畫面左側。 將欄位拖放至主區域。 要組合不同的元素，請將它們互相聯鎖以建立不同的組和/或組級別。 然後，您可以選取邏輯運算子來組合同一層級的元素：

* 和：兩個條件的交集。 只會考慮符合所有條件的元素。
* 或：兩個標準的聯合。 考慮匹配兩個條件中至少一個的元素。

![](../assets/journey64.png)

如果您使用[Adobe Experience Platform分段服務](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html)來建立區段，您可以在歷程條件中運用這些區段。 請參閱[在條件](../segment/using-a-segment.md)中使用區段。


>[!NOTE]
>
>您無法使用簡單編輯器對時間序列（例如購買清單、訊息的點按次數）執行查詢。 為此，您將需要使用進階編輯器。 請參閱[此頁面](../expression/expressionadvanced.md)。

當動作或條件發生錯誤時，個人的歷程就會停止。唯一能讓它繼續的方法就是勾選方塊 **[!UICONTROL Add an alternative path in case of a timeout or an error]**。請參閱[本節](../building-journeys/using-the-journey-designer.md#paths)。

## 資料來源條件 {#data_source_condition}

這可讓您根據資料來源的欄位或先前位於歷程中的事件，來定義條件。 若要了解如何使用運算式編輯器，請參閱[本頁面](../expression/expressionadvanced.md)。 使用進階運算式編輯器，您可以設定更進階的條件來處理集合，或使用需要傳遞參數的資料來源。 請參閱[此頁面](../datasource/external-data-sources.md)。

![](../assets/journey50.png)

## 時間條件{#time_condition}

這可讓您根據一天中的某小時和/或一週中的某天執行不同的動作。 例如，您可以決定在白天傳送SMS訊息，並在工作日的晚上傳送電子郵件。

>[!NOTE]
>
>時區不再是條件的特定時區，現在會在歷程屬性的歷程層級中定義。 請參見[此頁面](../building-journeys/timezone-management.md)。

![](../assets/journey51.png)

## 百分比分割 {#percentage_split}

此選項可讓您隨機分割對象，以定義每個群組的不同動作。 定義每個路徑的分割數和重新分割。 分割計算是統計的，因為系統無法預測歷程的此活動中會有多少人流量。 因此，分割的誤差範圍非常小。 此函式以Java隨機機制為基礎（請參閱此[page](https://docs.oracle.com/javase/7/docs/api/java/util/Random.html)）。

在測試模式中，達到分割時，一律會選取頂端分支。 如果希望測試選擇不同的路徑，則可以重新組織拆分分支的位置。 請參見[此頁面](../building-journeys/testing-the-journey.md)。

>[!NOTE]
>
>請注意，在百分比分割條件中沒有可新增路徑的按鈕。 路徑數取決於分割數。 在分割條件中，無法為其他情況新增路徑，因為路徑無法發生。 人們總是走在一條分道路上。

![](../assets/journey52.png)

## 日期條件 {#date_condition}

這可讓您根據日期定義不同的流程。 例如，如果人員在「銷售」期間進入步驟，您將向他發送特定消息。 今年剩下的時間，你會傳送另一條資訊。

>[!NOTE]
>
>時區不再是條件的特定時區，現在會在歷程屬性的歷程層級中定義。 請參閱[此頁面](../building-journeys/timezone-management.md)。

![](../assets/journey53.png)
