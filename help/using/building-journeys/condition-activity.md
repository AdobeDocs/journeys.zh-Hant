---
product: adobe campaign
title: 條件活動
description: 瞭解條件活動
feature: Journeys
role: User
level: Intermediate
exl-id: 7b44edbe-9d05-4d67-8a64-2a0a553fcb92
source-git-commit: d09d70a0ec2720c5a75385b9036bf3a6ab74f4ab
workflow-type: tm+mt
source-wordcount: '824'
ht-degree: 17%

---

# 條件活動{#section_e2n_pft_dgb}

有四種型別的條件可供使用：

* [資料Source條件](#data_source_condition)
* [時間條件](#time_condition)
* [百分比分割](#percentage_split)
* [日期條件](#date_condition)

![](../assets/journey49.png)

## 關於條件活動 {#about_condition}

在歷程中使用數個條件時，您可以為每個條件定義標籤，以更輕鬆地識別它們。

如果要定義多個條件，請按一下&#x200B;**[!UICONTROL Add a path]**。 對於每個條件，活動後都會在畫布中新增新路徑。

![](../assets/journey47.png)

請注意，歷程的設計具有功能影響。 在條件之後定義數個路徑時，只會執行第一個符合資格的路徑。 這表示您可以透過將路徑置於彼此上方或下方來改變路徑的優先順序。

例如，讓我們以第一個路徑的條件「Person is a VIP」以及第二個路徑的條件「Person is a male」為例。 如果同時符合兩個條件的人(身為VIP的男性)通過此步驟，即使他也符合第二個路徑的資格，也會選擇第一個路徑，因為第一個路徑「高於」。 若要變更此優先順序，請以另一個垂直順序移動您的活動。

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

在簡單編輯器中，您也會在事件和資料來源類別下方找到歷程屬性類別。 此類別包含與特定設定檔的歷程相關的技術欄位。 這是系統從即時歷程擷取的資訊，例如歷程 ID 或遇到的特定錯誤。 如需詳細資訊，請參閱[此頁面](../expression/journey-properties.md)

## 資料Source條件 {#data_source_condition}

這可讓您根據資料來源的欄位或先前位於歷程中的事件來定義條件。 若要瞭解如何使用運算式編輯器，請參閱[此頁面](../expression/expressionadvanced.md)。 使用進階運算式編輯器，您可以設定更進階的條件，以操控集合或使用需要傳遞引數的資料來源。 請參閱[此頁面](../datasource/external-data-sources.md)。

![](../assets/journey50.png)

## 時間條件{#time_condition}

這可讓您根據一天中的小時和/或星期來執行不同的動作。 例如，您可以決定在白天傳送SMS訊息，在工作日於夜間傳送電子郵件。

>[!NOTE]
>
>時區不再為條件所特有，現在會在歷程屬性中的歷程層級定義。 請參見[此頁面](../building-journeys/timezone-management.md)。

![](../assets/journey51.png)

## 百分比分割 {#percentage_split}

此選項可讓您隨機分割對象，以針對每個群組定義不同的動作。 定義每個路徑的分割數與重新分割區。 分割計算是統計性的，因為系統無法預測有多少人會在此歷程的活動中流動。 因此，分割的錯誤邊界非常低。 此函式以Java隨機機製為基礎（請參閱此[頁面](https://docs.oracle.com/javase/7/docs/api/java/util/Random.html)）。

在測試模式中，達到分割時，一律選擇頂端分支。 如果您希望測試選擇不同的路徑，可以重新組織分割分支的位置。 請參見[此頁面](../building-journeys/testing-the-journey.md)。

>[!NOTE]
>
>請注意，在百分比分割條件中沒有按鈕可新增路徑。 路徑的數量將取決於分割的次數。 在分割條件中，您無法針對其他情況新增路徑，因為它不會發生。 人們總是會進入其中一個分割路徑。

![](../assets/journey52.png)

## 日期條件 {#date_condition}

這可讓您根據日期定義不同的流程。 例如，如果人員在「銷售」期間進入步驟，您會將特定訊息傳送給他們。 在年餘下時間，您將傳送另一則訊息。

>[!NOTE]
>
>時區不再為條件所特有，現在會在歷程屬性中的歷程層級定義。 請參閱[此頁面](../building-journeys/timezone-management.md)。

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