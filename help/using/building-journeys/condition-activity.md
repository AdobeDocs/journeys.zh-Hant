---
product: adobe campaign
title: 條件活動
description: 瞭解條件活動
feature: Journeys
role: User
level: Intermediate
exl-id: 7b44edbe-9d05-4d67-8a64-2a0a553fcb92
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '869'
ht-degree: 16%

---

# 條件活動{#section_e2n_pft_dgb}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_



有四種型別的條件可供使用：

* [數據來源條件](#data_source_condition)
* [時間條件](#time_condition)
* [百分比分割](#percentage_split)
* [日期條件](#date_condition)

![](../assets/journey49.png)

## 關於條件活動 {#about_condition}

在歷程中使用多個條件時，您可以為每個條件定義標籤，以便更輕鬆地識別它們。

如果要定義多個條件，請按一下&#x200B;**[!UICONTROL Add a path]**。 針對每個條件，畫布中活動后新增路徑。

![](../assets/journey47.png)

請注意，旅程的設計具有功能影響。 在條件之後定義了多個路徑時，將僅執行第一個符合條件的路徑。 這意味著您可以通過將路徑放置在彼此的上方或下方來改變路徑的優先順序。

例如，讓我們以第一個路徑的條件“人是VIP”和第二個路徑的條件“人是男性”為例。 如果滿足兩個條件的人（VIP男性）通過了這一步，那麼如果他也有資格進入第二條道路，平均將選擇第一條路徑，因為第一條路徑是“高於”。 若要變更此優先順序，請以另一個垂直順序移動活動。

![](../assets/journey48.png)

您可以勾選&#x200B;**[!UICONTROL Show path for other cases than the one(s) above]**，為不符合定義條件的對象建立另一個路徑。 請注意，此選項不適用於分割條件。 請參閱[百分比分割](#percentage_split)。

簡單模式可讓您根據欄位組合執行簡單查詢。 所有可用的欄位都會顯示在螢幕的左側。將欄位拖放到主要區域中。若要合併不同的元素，請將它們互相聯鎖以建立不同的群組和/或群組層級。然後，您可以選取邏輯運算子來組合同一層級的元素：

* AND：兩個條件的交集。 只考慮符合所有條件的元素。
* OR：兩個條件的聯合。 考慮匹配兩個條件中至少一個的元素。

![](../assets/journey64.png)

如果您使用[Adobe Experience Platform Segmentation Service](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=zh-Hant)建立區段，可以在歷程條件中加以運用。 請參閱[在條件](../segment/using-a-segment.md)中使用區段。


>[!NOTE]
>
>使用簡單編輯器無法對時間序列執行查詢（例如購買清單、過去對訊息的點按）。 為此，您需要使用進階編輯器。 請參閱[此頁面](../expression/expressionadvanced.md)。

當動作或條件發生錯誤時，個人的歷程就會停止。唯一能讓它繼續的方法就是勾選方塊 **[!UICONTROL Add an alternative path in case of a timeout or an error]**。請參閱[本節](../building-journeys/using-the-journey-designer.md#paths)。

在簡單的編輯者中，您還可以在事件和資料來源類別下方找到“旅程”屬性類別。 此類別包含與給定設定檔的旅程相關的技術欄位。 這是系統從即時歷程擷取的資訊，例如歷程 ID 或遇到的特定錯誤。 有關詳細信息，請參閱 [此頁面](../expression/journey-properties.md)

## 數據來源條件 {#data_source_condition}

這允許您根據數據來源中的欄位或先前在歷程中定位的事件定義條件。 若要了解如何使用此運算式編輯者，請参閱 [此頁面](../expression/expressionadvanced.md)。 使用高級運算式編輯者，可以設置更高級的條件來作集合或使用需要傳遞參數的數據源。 請參閱[此頁面](../datasource/external-data-sources.md)。

![](../assets/journey50.png)

## 時間條件{#time_condition}

這可讓您根據一天中的某小時和/或一周中的某天執行不同的作。 例如，您可以決定在工作日白天發送 SMS 消息，在晚上發送電子郵件。

>[!NOTE]
>
>時區不再為條件所特有，現在會在歷程屬性中的歷程層級定義。 請參見[此頁面](../building-journeys/timezone-management.md)。

![](../assets/journey51.png)

## 百分比分割 {#percentage_split}

此選項可讓您隨機分割對象，以針對每個群組定義不同的動作。 定義每個路徑的分割數與重新分割區。 分割計算是統計性的，因為系統無法預測有多少人會在此歷程的活動中流動。 因此，分割的錯誤邊界非常低。 此函式以Java隨機機製為基礎（請參閱此[頁面](https://docs.oracle.com/javase/7/docs/api/java/util/Random.html)）。

在測試模式中，當達到分割時，始終選擇頂部分支。 如果您希望測試選擇其他路徑，則可以重新組織拆分分支的位置。 請參見[此頁面](../building-journeys/testing-the-journey.md)。

>[!NOTE]
>
>請注意，沒有按鈕在百分比分割條件中添加路徑。 路徑的數量將取決於拆分的數量。 在拆分條件下，不能為其他情況添加路徑，因為它不會發生。 人們總是會進入一條分裂的道路。

![](../assets/journey52.png)

## 日期條件 {#date_condition}

這允許您根據日期定義不同的流。 例如，如果此人在「銷售」期間進入該步驟，您將向他們發送特定消息。 在今年剩下的時間里，您將發送另一條消息。

>[!NOTE]
>
>時區不再特定於條件，現在在旅程屬性中的旅程級別定義。 請參閱[此頁面](../building-journeys/timezone-management.md)。

![](../assets/journey53.png)

<!--
## Profile cap {#profile_cap}

Use this condition type to set a maximum number of profiles for a journey path. When this limit is reached, the selected profiles take a second path.

You can use this condition type to ramp up the volume of your deliveries. For example, you might have recently moved to another email service provider, IP address, or email domain or subdomain. Using this feature, you can establish your reputation as a sender and avoid that your deliveries be blocked or moved to the spam folder of the recipients' mailbox. Learn how to increase your email reputation with IP warming in the [Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/generic-resources/increase-reputation-with-ip-warming.html){target="_blank"}.

The default cap is 1000. You must set an integer value that is greater than or equal to 1.

The counter applies only to the selected journey version. By default, the counter is reset to zero after 180 days. After a reset, the selected profiles take the first path again until the counter limit is reached. You can gradually increase this limit up to the total number of your subscribers. After your IP has warmed up, you can remove this condition.

The first path always has priority over the second path, even if you move the second path above the first path on the journey canvas.

![](../assets/profile-cap-condition.png)
-->