---
product: adobe campaign
title: 關於事件活動
description: 瞭解事件活動
feature: Journeys
role: User
level: Intermediate
exl-id: 3a4ff8b1-bbe7-47c8-9fba-defe4b1d5299
source-git-commit: 5b09ed456b6a9645dbb7897481317d3904e29d31
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---

# 關於事件活動 {#concept_rws_1rt_52b}

技術使用者設定的事件(請參閱 [此頁面](../event/about-events.md))都會顯示在畫面左側的浮動視窗第一個類別中。

![](../assets/journey43.png)

一律透過拖放事件活動來開始您的歷程。 您也可以連按兩下它。

![](../assets/journey44.png)

當您按一下畫布中的事件活動時，會顯示活動設定窗格。 根據預設，當您多次使用相同的事件時，會向畫布中的事件名稱新增一個遞增的數字。 此外，您可以使用 **[!UICONTROL Label]** 欄位，新增尾碼至事件名稱，該事件名稱會出現在畫布的活動下方。 這對於識別畫布中的事件很有用，尤其是如果您多次使用相同的事件。 它也會讓發生錯誤時的偵錯更容易，並讓報告更易於閱讀。

![](../assets/journey33.png)

## 在特定時間接聽事件

位於歷程中的事件活動會無限期監聽事件。 若要只在特定時間監聽事件，您必須為事件設定逾時。

接著，歷程會在逾時中指定的時間接聽事件。 若在該期間收到事件，則人員會進入事件路徑。 否則，客戶會進入逾時路徑或結束其歷程。

若要設定事件逾時，請遵循下列步驟：

1. 啟動 **[!UICONTROL Enable the event timeout]** 事件屬性中的選項。

1. 指定歷程將等待事件的時間長度。

1. 如果在指定的逾時內未收到任何事件時，要將個人傳送到逾時路徑中，請啟用 **[!UICONTROL Set the timeout path]** 選項。 如果未啟用此選項，則一旦達到逾時，個人將會結束歷程。

   ![](../assets/event-timeout.png)

在此範例中，歷程會傳送第一個歡迎推播給客戶。 然後只會在客戶隔天進入餐廳時傳送餐點折扣推播。 因此，我們將餐廳事件設定為1天逾時：

* 如果在歡迎推播後不到1天收到餐廳事件，則會傳送餐點折扣推播活動。
* 如果在隔天未收到餐廳事件，則人員會流經逾時路徑。

請注意，如果您想在之後放置的多個事件上設定逾時 **[!UICONTROL Wait]** 活動，您只需要針對這些事件之一設定逾時。

逾時將會套用至之後的所有事件。 **[!UICONTROL Wait]** 活動。 如果在指定的逾時前未收到任何事件，則個人將流入單一逾時路徑或結束其歷程。

![](../assets/event-timeout-group.png)
