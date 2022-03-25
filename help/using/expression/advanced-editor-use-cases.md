---
product: adobe campaign
title: 使用進階運算式編輯器
description: 瞭解如何建立進階運算式
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 724ae59e-d1b5-4de9-b140-d37064e22ac6
source-git-commit: a5d063784b278120b61f8d2641264baf40e34a90
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---

# 高級表達式示例

「高級」表達式編輯器可用於建立條件，以便篩選您的行程中的用戶。 通過這些條件，您可以按時間、日期、位置、持續時間或諸如購買或放棄購物車之類的操作來瞄準用戶，以便在行程中重新確定用戶的目標。

>[!NOTE]
>
>事件以@開頭，資料源以#開頭。

## 在體驗事件上建立條件

高級表達式編輯器是對時間系列執行查詢（如購買清單或以前對消息的按一下）的必備項。 無法使用簡單編輯器執行此類查詢。

從Adobe Experience Platform以按時間順序倒序的集合檢索經驗事件，因此：

* 第一個函式將返回最近的事件
* 最後一個函式將返回最舊的函式。

例如，假設您希望在過去7天內放棄購物車的客戶在客戶接近商店時發送一條消息，並針對他們希望在商店中購買的物品提供優惠。

**您需要構建以下條件：**

首先，目標客戶在過去7天內瀏覽了線上商店但未完成訂單。

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**此表達式查找此用戶在過去7天中指定的所有事件：**

然後，它將選擇所有未轉換為completePurchase的addtocart事件。

>[!NOTE]
>
>要快速在表達式中插入欄位，請按兩下編輯器左面板中的欄位。

指定的時間戳用作日期時間值，第二個是天數。

```json
        in( "addToCart", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
        and
        not(in( "completePurchase", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction}))
```

此表達式返回布爾值。

**現在，我們構建一個表達式，檢查產品是否在庫存中**

* 在庫存中，此表達式將查找產品的數量欄位並指定其應大於0。

`#{Inventory.fieldgroup3.quantity} > 0`

* 在右側，指定了必要的值，在此，我們需要檢索儲存的位置，該位置是從事件「ErvirLumaStudio」的位置映射的：

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* 使用函式指定SKU `first` 要檢索最近的「addToCart」交互元件：

   ```json
       #{ExperiencePlatformDataSource
                       .ExperienceEventFieldGroup
                       .experienceevent
                       .first(
                       currentDataPackField
                       .productData
                       .productInteraction == "addToCart"
                       )
                       .SKU}
   ```

在此處，您可以在行程中添加其他路徑，以便在產品不在商店時使用，並通過訂約優惠發送通知。 相應地配置消息並使用個性化資料來增強消息目標。

## 使用高級表達式編輯器進行字串操作的示例

**條件**

此條件僅檢索在「阿靈頓」中觸發的地理事件：

```json
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

說明：這是嚴格的字串比較（區分大小寫），相當於在簡單模式下使用的查詢 `equal to` 與 `Is sensitive` 選中。

與 `Is sensitive` 取消選中將在高級模式下生成以下表達式：

```json
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**在操作中**

以下表達式允許您在操作個性化欄位中定義CRM ID:

```json
substr(
   @{MobileAppLaunch
   ._myorganization
   .identification
   .crmid},
   1, 
   lastIndexOf(
     @{MobileAppLaunch
     ._myorganization
     .identification
     .crmid},
     '}'
   )
)
```

說明：此示例使用 `substr` 和 `lastIndexOf` 函式，用於刪除用移動應用啟動事件傳遞的CRM ID所包圍的大括弧。

有關如何使用高級表達式編輯器的詳細資訊，請觀察 [這個視頻](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/create-a-journey.html)。
