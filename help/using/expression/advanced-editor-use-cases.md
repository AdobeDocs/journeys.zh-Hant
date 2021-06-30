---
product: adobe campaign
title: 使用進階運算式編輯器
description: 瞭解如何建立進階運算式
feature: 歷程
role: Data Engineer
level: Experienced
exl-id: 724ae59e-d1b5-4de9-b140-d37064e22ac6
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 2%

---

# 進階運算式範例

進階運算式編輯器可用來建立條件，以便您篩選歷程中的使用者。 這些條件可讓您依時間、日期、位置、期間或購買或放棄購物車等動作來鎖定使用者，以便在歷程中重新鎖定使用者。

>[!NOTE]
>
>事件以@開頭，資料來源以#開頭。

## 在體驗事件上建立條件

進階運算式編輯器是強制性的，可對時間序列執行查詢，例如購買清單或以前對訊息的點按。 無法使用簡單編輯器執行此類查詢。

體驗事件會以反向時間順序從Adobe Experience Platform擷取為集合，因此：

* 第一個函式會傳回最近的事件
* 最後一個函式將返回最舊的函式。

例如，假設您想要鎖定在過去7天內放棄購物車的客戶，在客戶接近商店時傳送訊息，並針對他想要的商店項目提供優惠。

**您需要建立下列條件：**

首先，目標客戶瀏覽了線上商店，但未在過去7天內完成訂單。

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**此運算式會尋找此使用者在過去7天中指定的所有事件：**

接著，系統會選取所有未轉換為completePurchase的addtocart事件。

>[!NOTE]
>
>若要快速插入運算式中的欄位，請連按兩下編輯器左側面板中的欄位。

指定的時間戳記作為日期時間值，秒為天數。

```
        In( “addToCart”, #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
        And
        Not(In( “completePurchase”, #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
```

此運算式會傳回布林值。

**現在來建立運算式，檢查產品是否有存貨**

* 在「庫存」中，此運算式會尋找產品的數量欄位，並指定其應大於0。

`#{Inventory.fieldgroup3.quantity} > 0`

* 在右側，需要指定必要值，在此處，我們需要檢索儲存區的位置，該位置是從事件「AmmirdLumaStudio」的位置映射的：

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* 並指定SKU，使用函式`first`來擷取最新的「addToCart」互動：

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

從那裡，您可以在歷程中新增產品不在商店時的其他路徑，並透過參與優惠方案傳送通知。 相應地設定訊息，並使用個人化資料來增強訊息目標。

## 使用進階運算式編輯器處理字串的範例

**條件**

此條件僅會擷取「Arlington」中觸發的地理柵欄事件：

```
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

說明：這是嚴格的字串比較（區分大小寫），等同於簡單模式中使用`equal to`且已勾選`Is sensitive`的查詢。

取消勾選`Is sensitive`的相同查詢會在進階模式中產生下列運算式：

```
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**在動作中**

下列運算式可讓您在動作個人化欄位中定義CRM ID:

```
    substr(@{MobileAppLaunch
            ._myorganization
            .identification
            .crmid}, 1, 
            lastIndexOf(@{MobileAppLaunch
                        ._myorganization
                        .identification
                        .crmid}
                         }
                         ))
```

說明：此範例使用`substr`和`lastIndexOf`函式來移除大括弧，此大括弧會包含隨行動應用程式啟動事件傳遞的CRM ID。

有關如何使用高級表達式編輯器的詳細資訊，請觀看[此視頻](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/create-a-journey.html)。
