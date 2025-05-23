---
product: adobe campaign
title: 關於事件活動
description: 瞭解事件活動
feature: Journeys
role: User
level: Intermediate
exl-id: 3a4ff8b1-bbe7-47c8-9fba-defe4b1d5299
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 1%

---

# 關於事件活動 {#concept_rws_1rt_52b}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_


技術使用者設定的事件（請參閱[此頁面](../event/about-events.md)）都會顯示在畫面左側的浮動視窗的第一個類別中。

![](../assets/journey43.png)

一律透過拖放事件活動來開始您的歷程。 您也可以連按兩下它。

![](../assets/journey44.png)

當您按一下畫布中的事件活動時，會顯示活動設定窗格。 根據預設，當您多次使用相同的事件時，會向畫布中的事件名稱新增一個遞增的數字。 此外，您可以使用&#x200B;**[!UICONTROL Label]**&#x200B;欄位將尾碼新增至事件名稱，該事件名稱將會顯示在畫布的活動下方。 這對於識別畫布中的事件很有用，尤其是如果您多次使用相同的事件。 它也會讓發生錯誤時的偵錯更容易，並讓報告更易於閱讀。

![](../assets/journey33.png)

## 在特定期間接聽事件 {#listening}

位於歷程中的事件活動會無限期監聽事件。 若要只在特定時間監聽事件，您必須為事件設定逾時。

接著，歷程會在逾時中指定的時間接聽事件。 若在該期間收到事件，則人員會進入事件路徑。 如果沒有，客戶會進入逾時路徑（如果已定義），或繼續該歷程。 如果未定義逾時路徑，則逾時設定會當作等待活動，讓設定檔等候一段時間，如果事件發生在該等待結束之前，便會停止該時間。 如果您想要在逾時後從歷程中排除設定檔，您必須設定逾時路徑。

若要設定事件逾時，請遵循下列步驟：

1. 從事件屬性啟動&#x200B;**[!UICONTROL Enable the event timeout]**&#x200B;選項。

1. 指定歷程將等待事件的時間長度。

1. 若您想在指定的逾時時間內未收到任何事件時，將個人傳送至逾時路徑，請啟用&#x200B;**[!UICONTROL Set the timeout path]**&#x200B;選項。 如果未啟用此選項，則到達逾時時間後，個人將繼續歷程。

   ![](../assets/event-timeout.png)

在此範例中，歷程會傳送第一個歡迎推播給客戶。 然後只會在客戶隔天進入餐廳時傳送餐點折扣推播。 因此，我們將餐廳事件設定為1天逾時：

* 如果在歡迎推播後不到1天收到餐廳事件，則會傳送餐點折扣推播活動。
* 如果在隔天未收到餐廳事件，則人員會流經逾時路徑。

請注意，如果您想要在&#x200B;**[!UICONTROL Wait]**&#x200B;活動後定位的多個事件上設定逾時，您只需要在這些事件之一上設定逾時。

逾時將套用至&#x200B;**[!UICONTROL Wait]**&#x200B;活動之後放置的所有事件。 如果在指定的逾時前未收到任何事件，則個人將流入單一逾時路徑，或將繼續該歷程通過分支退出已定義這些逾時設定的活動。

![](../assets/event-timeout-group.png)
