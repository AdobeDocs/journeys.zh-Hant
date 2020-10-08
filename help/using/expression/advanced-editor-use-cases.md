---
title: 使用進階運算式編輯器
description: 瞭解如何建立進階運算式
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: benzaama
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 2%

---


# 使用進階運算式編輯器

「進階運算式」編輯器可用來建立條件，讓您在歷程中篩選使用者。 這些條件可讓您依時間、日期、位置、持續時間或購買或放棄購物車等動作來定位使用者，以便在歷程中重新定位使用者。

>[!NOTE]
>
>事件以@開頭，資料來源以#開頭。

## 建立體驗事件的條件

進階運算式編輯器是對時間系列執行查詢（例如購買清單或過去點按訊息）的強制性。 不能使用簡單編輯器執行此類查詢。

體驗事件是從Adobe Experience Platform以反向時間順序擷取為系列，因此：

* first函式將傳回最近的事件
* 最後一個函式會傳回最舊的函式。

例如，假設您想要定位在最近7天內放棄購物車的客戶，以便在客戶接近商店時傳送訊息，並針對他想要的商店商品提供優惠。

**您需要建立下列條件：**

首先，目標客戶是在過去7天內瀏覽線上商店但未完成訂單的客戶。

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**此運算式會尋找此使用者在過去7天內指定的所有事件：**

然後，它會選取所有未轉換為completePurchase的購物車事件。

>[!NOTE]
>
>若要快速插入運算式中的欄位，請連按兩下編輯器左側面板中的欄位。

指定的時間戳記會當成日期時間值，第二個是天數。

    &quot;
    In(&quot;addToCart&quot;, #{ExperiencePlatformDataSource
    .ExperienceEventFieldGroup
    .experienceevent
    .all(在
    LastDays(currentDataPackField.timestamp, 7))
    .productData
    
    
    
    
    
    
    
    
    
    
    .productInteraction})AndNot(In(&quot;completePurchase&quot;, #{ExperiencePlatformDataSourceExperienceEventGroupLastEvent.ExperienceCurrentField.7)All(In&#39;DataField.Pack, 7Product DataInteraction)。&quot;

此運算式會傳回布林值。

**現在，讓我們建立運算式檢查產品是否有存貨**

* 在「庫存」中，此運算式會尋找產品的數量欄位，並指定其大於0。

`#{Inventory.fieldgroup3.quantity} > 0`

* 在右側，指定了必要值，在此，我們需要檢索儲存的位置，該位置是從事件&quot;ArricLumaStudio&quot;的位置映射的：

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* 並指定SKU，使用函式 `first` 來擷取最近的「addToCart」互動：

   ```
       #{ExperiencePlatformDataSource
                       .ExperienceEventFieldGroup
                       .experienceevent
                       .first(
                       currentDataPackField
                       .productData
                       .productInteraction == “addToCart”
                       )
                       .SKU}
   ```

從此，您可以在歷程中新增另一個途徑，瞭解產品何時不在商店，並透過參與選件傳送通知。 相應地配置消息並使用個性化資料增強消息目標。

## 使用進階運算式編輯器處理字串的範例

**條件**

此條件僅擷取在&quot;Arlington&quot;中觸發的地理事件：

    &quot;
    @{GeofenceEntry
    .placeContext
    .POIinteraction
    .POIDetail
    .name} == &quot;Arlington&quot;
    &quot;

說明：這是嚴格的字串比較（區分大小寫），等同於使用勾選的簡單模式 `equal to` 的查 `Is sensitive` 詢。

在進階模式中， `Is sensitive` 取消選取的相同查詢將產生下列運算式：

    &quot;
    equalIgnoreCase(@{GeofenceEntry
    .placeContext
    .POIinteraction
    .POIDetail
    .name}, &quot;Arlington&quot;)
    
    &quot;

**實際操作**

下列運算式可讓您在動作個人化欄位中定義CRM ID:

    &quot;
    substr(@{MobileAppLaunch
    。_myorganization
    .identification
    .crmid}, 1,
    lastIndexOf(@{MobileAppLaunch
    。_myorganization
    .identification
    .crmid}
    }
    )
    
    &quot;

說明：此範例使用 `substr` 和函 `lastIndexOf` 數來移除大括弧，此大括弧會括住隨行動應用程式啟動事件傳遞的CRM ID。

如需如何使用進階運算式編輯器的詳細資訊，請觀看 [此影片](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/create-a-journey.html)。
