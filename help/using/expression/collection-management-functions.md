---
product: adobe campaign
title: 收集管理函式
description: 瞭解集合管理功能中的資料類型
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

表達式語言還引入了一組函式來查詢集合。

這些功能在下面說明。 在以下示例中，讓我們使用包含集合的事件負載：

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

的 **[!UICONTROL all]** 函式通過使用布爾表達式來啟用給定集合上的篩選器定義。

```json
<listExpression>.all(<condition>)
```

例如，在所有應用用戶中，您可以使用IOS13(布爾表達式「app used ==IOS13」)獲取這些用戶。 此函式的結果是包含與布爾表達式匹配的項的篩選清單(例如：app user 1、app user 34、app user 432)。

在「資料源條件」活動中，您可以檢查 **[!UICONTROL all]** 函式為null或不為null。 您也可以將此 **[!UICONTROL all]** 與其他函式(如 **[!UICONTROL count]**。 有關詳細資訊，請參見 [資料源條件活動](../building-journeys/condition-activity.md#data_source_condition)。

**範例 1:**

我們要檢查用戶是否安裝了特定版本的應用程式。 為此，我們將獲得與版本為1.0的移動應用程式關聯的所有推送通知令牌。然後，我們用 **[!UICONTROL count]** 函式，檢查返回的令牌清單是否包含至少一個元素。

```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

結果是真的。

**範例 2:**

我們用 **[!UICONTROL count]** 函式，以檢查集合中是否存在推送通知令牌。

```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```

結果將是真的。

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
>當 **all()** 函式為空，篩選器將返回清單中的所有元素。 **但是，為了計算集合的元素數，不需要全部函式。**


```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

表達式的結果是 **3**。

**範例 3:**

在這裡，我們檢查過去24小時內是否有人未收到任何通信。 我們使用兩個基於集合中兩個元素的表達式來過濾從ExperiencePlatform資料源檢索到的體驗事件集合。 特別是，將事件的時間戳與 **[!UICONTROL nowWithDelta]** 的子菜單。

```json
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

如果沒有與這兩個條件相匹配的體驗事件，則結果為true。

**範例 4:**

在此，我們要檢查某個人在過去7天內是否至少啟動了一次應用程式，以便例如觸發推式通知，邀請他們啟動教程。

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
>操作資料源集合時。 處理使用 **[!UICONTROL all]**。 **[!UICONTROL first]** 和 **[!UICONTROL last]**我們
>逐個循環。 **[!UICONTROL currentEventField]** 和 **currentDataPackField**
>與所環繞的元素相對應。

**函式&quot;first(`<condition>`)和「last(`<condition>`)&quot;**

的 **[!UICONTROL first]** 和 **[!UICONTROL last]** 函式還在返回滿足篩選器的清單的第一個/最後一個元素時啟用集合中篩選器的定義。

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**範例 1:**

此表達式返回與版本為1.0的移動應用程式關聯的第一個推送通知令牌。

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

結果為&quot;token_1&quot;。

**範例 2:**

此表達式返回與版本為1.0的移動應用程式關聯的最後一個推送通知令牌。

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

結果為&quot;token_2&quot;。

>[!NOTE]
>
>從Adobe Experience Platform以按時間順序倒序的集合來檢索經驗事件，因此：
>
>* **[!UICONTROL first]** 函式將返回最近的事件
>* **[!UICONTROL last]** 函式將返回最舊的函式。


**範例 3:**

我們檢查DMA ID的第一個（最近的）Adobe Analytics事件（其值非零）是否具有等於602的值。

```json
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**函式「at(`<index>`)&quot;**

的 **[!UICONTROL at]** 函式，可根據索引引用集合中的特定元素。
索引0是集合的第一個索引。

_`<listExpression>`.at(`<index>`)_

**範例：**

此表達式返回清單的第二個推送通知令牌。

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

結果為&quot;token_2&quot;。

**其他示例**

```json
#{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent. all(currentDataPackField._aepgdcdevenablement2.purchase_event.receipt_nbr == "10-337-4016"). 
_aepgdcdevenablement2.purchase_event.productListItems. all(currentDataPackField.SKU == "AB17 1234 1775 19DT B4DR 8HDK 762").name}
```

```json
 #{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent.last(
currentDataPackField.eventType == "commerce.productListAdds").productListItems.last(currentDataPackField.priceTotal >= 150).name}
```
