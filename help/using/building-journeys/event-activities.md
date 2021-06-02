---
product: adobe campaign
title: 關於事件活動
description: 了解事件活動
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 3a4ff8b1-bbe7-47c8-9fba-defe4b1d5299
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 1%

---

# 關於事件活動 {#concept_rws_1rt_52b}

技術使用者設定的事件（請參閱[此頁面](../event/about-events.md)）全部顯示在畫面左側浮動視窗的第一個類別中。

![](../assets/journey43.png)

一律透過拖放事件活動來開始您的歷程。 您也可以按兩下。

![](../assets/journey44.png)

當您按一下畫布中的事件活動時，會顯示活動設定窗格。 依預設，當您多次使用相同事件時，畫布中的事件名稱會新增遞增的數字。 此外，您可以使用&#x200B;**[!UICONTROL Label]**&#x200B;欄位，將尾碼新增至事件名稱，該名稱將顯示在畫布中的活動底下。 這對於在畫布中識別事件很實用，尤其是當您多次使用相同事件時。 這也可讓除錯在發生錯誤時更輕鬆，且讓報表更容易讀取。

![](../assets/journey33.png)

## 在特定時間內接聽事件

位於歷程中的事件活動會無限期監聽事件。 若要僅在特定時間監聽事件，您必須為事件設定逾時。

然後，歷程會在逾時中指定的時間內監聽事件。 若在該期間收到事件，則人員將會流入事件路徑。 若非如此，客戶會流入逾時路徑，或結束其歷程。

若要設定事件的逾時，請執行下列步驟：

1. 從事件屬性中啟動&#x200B;**[!UICONTROL Enable the event timeout]**&#x200B;選項。

1. 指定歷程等待事件的時間長度。

1. 如果要在指定超時內未收到任何事件時將個人發送到超時路徑，請啟用&#x200B;**[!UICONTROL Set the timeout path]**&#x200B;選項。 如果未啟用此選項，一旦逾時，個別的歷程就會結束。

   ![](../assets/event-timeout.png)

在此範例中，歷程會傳送第一個歡迎推播給客戶。 然後，只有在客戶在隔天內進入餐廳時，才會傳送餐點折扣推播。 因此，我們已將餐廳事件設定為1天逾時：

* 如果在歡迎推播後不到1天收到餐廳事件，則會傳送餐點折扣推播活動。
* 如果隔天內未收到餐廳事件，則人員會透過逾時路徑流動。

請注意，如果您想要對位於&#x200B;**[!UICONTROL Wait]**&#x200B;活動之後的多個事件設定逾時，您只需要對其中一個事件設定逾時。

逾時會套用至&#x200B;**[!UICONTROL Wait]**&#x200B;活動之後放置的所有事件。 如果在指定的逾時前未收到任何事件，則個人會流入單一逾時路徑，或結束其歷程。

![](../assets/event-timeout-group.png)
