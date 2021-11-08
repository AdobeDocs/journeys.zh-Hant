---
product: adobe campaign
title: 收集管理函式
description: 了解集合管理功能中的資料類型
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: e80b04fe-b2d3-4c1b-ba22-7e37a9ad1d57
source-git-commit: 579e5a0dbdc11369248c2683c399b090130a7262
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 2%

---

# 收集管理函式 {#collection-management-functions}

運算式語言也導入了一組函式來查詢集合。

以下說明這些函式。 在下列範例中，我們將使用包含集合的事件裝載：

```json
                { 
   "_experience":{ 
      "campaign":{ 
         "message":{ 
            "profile":{ 
               "pushNotificationTokens":[ 
                  { 
                     "token":"token_1",
                     "application":{ 
                        "_id":"APP1",
                        "name":"MarltonMobileApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_2",
                     "application":{ 
                        "_id":"APP2",
                        "name":"MarketplaceApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_3",
                     "application":{ 
                        "_id":"APP3",
                        "name":"VendorApp",
                        "version":"2.0"
                     }
                  }
               ]
            }
         }
      }
   },
   "timestamp":"1536160728"
}
```

**函式&quot;all(`<condition>`)&quot;**

此 **[!UICONTROL all]** 函式會使用布林運算式，來啟用指定集合上的篩選器定義。

```json
<listExpression>.all(<condition>)
```

例如，在所有應用程式使用者中，您可以使用IOS 13取得使用者(布林運算式「app used == IOS 13」)。 此函式的結果是篩選清單，其中包含符合布林運算式的項目(範例：應用程式使用者1、應用程式使用者34、應用程式使用者432)。

在「資料來源條件」活動中，您可以檢查 **[!UICONTROL all]** 函式為null或非null。 您也可以結合 **[!UICONTROL all]** 函式與其他函式(例如 **[!UICONTROL count]**. 如需詳細資訊，請參閱 [資料來源條件活動](../building-journeys/condition-activity.md#data_source_condition).

**範例 1:**

我們想檢查使用者是否已安裝特定版本的應用程式。 為此，我們會取得與版本為1.0的行動應用程式相關聯的所有推播通知Token。然後，我們會使用 **[!UICONTROL count]** 函式，以檢查傳回的Token清單是否包含至少一個元素。

```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

結果為true。

**範例 2:**

在此，我們使用 **[!UICONTROL count]** 函式來檢查集合中是否有推播通知Token。

```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```

結果為true。

<!--Alternatively, you can check if there is no token in the collection:

   ```json
   count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) == 0
   ```

The result will be false.

Here we use the count function in a condition to count the number of push notification tokens in the event.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token})`

The result is true.

Note that when the condition in the **all()** function is empty, the filter will return all the elements in the list. Hence, the expression above is equivalent to:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.application.name})`

In both cases, the result of the expression is **3**.

A query of experience events recorded on the Adobe Experience Platform may or may not include the current event that triggered the current Journey. This will depend on the relative processing time with which [!DNL Journey Orchestration] sees an event and started evaluating conditions, versus the time it takes for that event to be ingested into the Adobe Experience Platform. For example, when using the .all() syntax to query experience events from the Adobe Experience Platform, we recommend enforcing the exclusion of the current event (by requiring an
earlier timestamp) in order to only consider prior events.-->

>[!NOTE]
>
>若 **all()** 函式為空，則篩選器會傳回清單中的所有元素。 **不過，若要計算集合的元素數，不需要所有函式。**


```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

運算式的結果為 **3**.

**範例 3:**

在此，我們會檢查過去24小時內個人是否未收到任何通訊。 我們會根據集合的兩個元素，使用兩個運算式來篩選從ExperiencePlatform資料來源擷取的體驗事件集合。 尤其是，事件的時間戳記會與 **[!UICONTROL nowWithDelta]** 函式。

```json
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

如果沒有符合這兩個條件的體驗事件，則結果為true。

**範例 4:**

在此，我們想檢查個人是否在過去7天內至少啟動了一次應用程式，以便例項觸發推播通知並邀請他們啟動教學課程。

```json
count(
 #{ExperiencePlatform.AnalyticsData.experienceevent.all(
 nowWithDelta(-7,"days") <= currentDataPackField.timestamp
 and currentDataPackField.application.firstLaunches.value > 0
)._id}) > 0
```

<!--**"All + Count" example 4:** here we use the count function in a boolean expression to see if there is push notification tokens in the collection.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) > 0`

The result will be:

`true`

Alternatively, you can check if there is NO token in the collection:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) =0`

The result will be:

`false`-->

>[!NOTE]
>
>**[!UICONTROL currentEventField]** 僅在操作事件集合和 **currentDataPackField**
>處理資料源集合時。 使用處理集合時 **[!UICONTROL all]**, **[!UICONTROL first]** 和 **[!UICONTROL last]**，我們
>逐一循環在集合的每個元素上。 **[!UICONTROL currentEventField]** 和 **currentDataPackField**
>對應於循環的元件。

**函式&quot;first(`<condition>`)」和「last(`<condition>`)&quot;**

此 **[!UICONTROL first]** 和 **[!UICONTROL last]** 函式也會在傳回符合篩選的清單的第一個/最後一個元素時，啟用集合上篩選器的定義。

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**範例 1:**

此運算式會傳回與版本為1.0的行動應用程式相關聯的第一個推播通知Token。

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

結果為「token_1」。

**範例 2:**

此運算式會傳回與版本為1.0的行動應用程式相關聯的最後一個推播通知Token。

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

結果為「token_2」。

>[!NOTE]
>
>體驗事件會以反向時間順序從Adobe Experience Platform擷取為集合，因此：
>
>* **[!UICONTROL first]** 函式會傳回最近的事件
>* **[!UICONTROL last]** 函式會傳回最舊的函式。


**範例 3:**

我們會檢查DMA ID的第一個（最近的）Adobe Analytics事件（值非零）是否有等於602的值。

```json
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**函式&quot;at(`<index>`)&quot;**

此 **[!UICONTROL at]** 函式可讓您根據索引參考集合中的特定元素。
索引0是集合的第一個索引。

_`<listExpression>`.at(`<index>`)_

**範例：**

此運算式會傳回清單的第二個推播通知Token。

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

結果為「token_2」。

**其他範例**

```json
#{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent. all(currentDataPackField._aepgdcdevenablement2.purchase_event.receipt_nbr == "10-337-4016"). 
_aepgdcdevenablement2.purchase_event.productListItems. all(currentDataPackField.SKU == "AB17 1234 1775 19DT B4DR 8HDK 762").name}
```

```json
 #{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent.last(
currentDataPackField.eventType == "commerce.productListAdds").productListItems.last(currentDataPackField.priceTotal >= 150).name}
```
