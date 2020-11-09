---
title: 關於事件活動
description: 瞭解活動活動
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: e353d593ab2710f50a88a3715378c86c2e37b4f6
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---


# 關於事件活動 {#concept_rws_1rt_52b}

技術使用者設定的事件(請參 [閱本頁](../event/about-events.md))都會顯示在螢幕左側的浮動視窗第一類別中。

![](../assets/journey43.png)

透過拖放活動，始終從您的旅程開始。 您也可以按兩下它。

![](../assets/journey44.png)

當您按一下畫布中的事件活動時，會顯示活動設定窗格。 依預設，當您多次使用相同事件時，畫布中的事件名稱會新增遞增的數字。 此外，您也可以使用欄 **[!UICONTROL Label]** 位為事件名稱新增尾碼，事件名稱會顯示在畫布中的活動下方。 這對於識別畫布中的事件非常有用，尤其是當您使用相同事件多次時。 此外，在發生錯誤時，除錯也會更輕鬆，並讓報表更容易閱讀。

![](../assets/journey33.png)

## 在特定時間內監聽事件

位於歷程中的事件活動會無限期地監聽事件。 若要僅在特定時間監聽事件，您必須設定事件逾時。

然後，歷程將在逾時中指定的時間內監聽事件。 如果在該期間收到事件，則人員將在事件路徑中流動。 如果沒有，客戶將流入逾時路徑，或結束其歷程。

若要設定事件的逾時，請依照下列步驟進行：

1. 從事件 **[!UICONTROL Enable the event timeout]** 屬性啟用選項。

1. 指定歷程等待活動的時間長度。

1. 如果您想在指定逾時內未收到任何事件時，將個人傳送至逾時路徑，請啟用選 **[!UICONTROL Set the timeout path]** 項。 如果未啟用此選項，則到達逾時後，個人的歷程將結束。

   ![](../assets/event-timeout.png)

在此範例中，歷程會傳送第一個歡迎推播給客戶。 然後，只有當顧客在第二天進入餐廳時，它才會發送餐點折扣推播。 因此，我們設定餐廳事件為1天逾時：

* 如果在歡迎推播後不到1天收到餐廳活動，則會傳送餐點折扣推播活動。
* 如果第二天未收到餐廳事件，則訪客會透過逾時路徑流程。

請注意，如果您想要針對活動後定位的多個事件設定逾時， **[!UICONTROL Wait]** 則只需針對這些事件設定逾時。

逾時會套用至活動後所定位的所有事 **[!UICONTROL Wait]** 件。 如果在指定逾時後未收到任何事件，則個人會流入單一逾時路徑，或結束其歷程。

![](../assets/event-timeout-group.png)
