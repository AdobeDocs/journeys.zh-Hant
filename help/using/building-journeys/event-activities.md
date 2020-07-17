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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 71b5b1ecd20056d0103ae1a8b83a31478449e844
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 0%

---


# 關於事件活動 {#concept_rws_1rt_52b}

由技術使用者設定的事件(請 [](../event/about-events.md)參閱)都會顯示在畫面左側浮動視窗的第一類別中。

![](../assets/journey43.png)

透過拖放活動，始終從您的旅程開始。 您也可以按兩下它。

![](../assets/journey44.png)

當您按一下畫布中的事件活動時，會顯示活動設定窗格。 依預設，當您多次使用相同事件時，畫布中的事件名稱會新增遞增的數字。 此外，您也可以使用欄 **[!UICONTROL Label]** 位為事件名稱新增尾碼，事件名稱會顯示在畫布中的活動下方。 這對於識別畫布中的事件非常有用，尤其是當您使用相同事件多次時。 此外，在發生錯誤時，除錯也會更輕鬆，並讓報表更容易閱讀。

![](../assets/journey33.png)

## 進階使用： 並行等待的事件{#section_vxv_h25_pgb}

**您如何只在特定時間內才能聆聽活動？**

位於歷程中的事件活動會無限期地監聽事件。 若要僅在特定時間監聽事件，您必須新增與事件路徑平行的等待活動。 然後，該歷程將在等待活動中指定的時間內偵聽事件。 如果在該期間收到事件，則人員將在事件路徑中流動。 否則，客戶將流入等待路徑。

例如，您先將歡迎推播傳送給客戶，而且您只想在客戶在6小時內進入餐廳時傳送餐點折扣推播。 若要這麼做，您將建立第二個路徑（與餐廳事件一平行），並有6小時的等待活動。 如果在歡迎推播後不到6小時收到餐廳活動，則會傳送餐點折扣推播活動。 如果未在接下來的6小時內收到任何餐廳事件，則該人員會流過等待路徑。

![](../assets/journeyuc2_31.png)
