---
product: adobe campaign
solution: Journey Orchestration
title: 收集管理函式
description: 瞭解收集管理功能中的資料類型
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 1%

---


# 收集管理函式 {#collection-management-functions}

運算式語言也提供一組函式來查詢系列。

以下說明這些函式。 在下列範例中，讓我們使用包含系列的事件裝載：

```
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

**[!UICONTROL all]**&#x200B;函式可使用布林運算式來定義指定系列上的篩選器。

```
<listExpression>.all(<condition>)
```

例如，在所有應用程式使用者中，您都可以取得使用IOS 13的使用者（布林運算式&quot;app used == IOS 13&quot;）。 此函式的結果是包含與布爾表達式匹配的項目的篩選清單(例如：app user 1、app user 34、app user 432)。

在「資料源條件」活動中，您可以檢查&#x200B;**[!UICONTROL all]**&#x200B;函式的結果是否為空。 您也可以將此&#x200B;**[!UICONTROL all]**&#x200B;函式與其他函式（例如&#x200B;**[!UICONTROL count]**）結合。 如需詳細資訊，請參閱[資料來源條件活動](../building-journeys/condition-activity.md#data_source_condition)。

**範例1:**

我們想檢查使用者是否已安裝特定版本的應用程式。 為此，我們會取得與版本為1.0的行動應用程式相關的所有推播通知Token。然後，我們使用&#x200B;**[!UICONTROL count]**&#x200B;函式執行條件，以檢查傳回的Token清單是否包含至少一個元素。

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

結果是正確的。

**範例2:**

在這裡，我們使用&#x200B;**[!UICONTROL count]**&#x200B;函式來檢查系列中是否有推播通知Token。

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```

結果是正確的。

<!--Alternatively, you can check if there is no token in the collection:

   ```
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
>當&#x200B;**all()**&#x200B;函式中的篩選條件為空時，篩選器將返回清單中的所有元素。 **不過，為了計算系列的元素數目，並不需要所有函式。**


```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

表達式的結果為&#x200B;**3**。

**範例3:**

在此，我們會檢查過去24小時內是否有個人收到任何通訊。 我們會使用兩個基於系列兩個元素的運算式，來篩選從ExperiencePlatform資料來源擷取的體驗事件集合。 尤其是，事件的時間戳記會與&#x200B;**[!UICONTROL nowWithDelta]**&#x200B;函式傳回的dateTime進行比較。

```
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

如果沒有與兩個條件相符的體驗事件，則結果為true。

**範例4:**

在這裡，我們想檢查個人在過去7天中是否至少啟動過一次應用程式，例如觸發推播通知，邀請他開始教學課程。

```
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
>**[!UICONTROL currentEventField]** 僅在控制事件集合和currentDataPackField時 **可用**
>控制資料來源集合時。 當處理具有&#x200B;**[!UICONTROL all]**、**[!UICONTROL first]**&#x200B;和&#x200B;**[!UICONTROL last]**的系列時，我們
>逐個循環顯示系列的每個元素。 **[!UICONTROL currentEventField]** 和 **currentDataPackField**
>對應於所循環的元素。

**函式&quot;first(`<condition>`)&quot;和&quot;last(`<condition>`)&quot;**

**[!UICONTROL first]**&#x200B;和&#x200B;**[!UICONTROL last]**&#x200B;函式也可啟用系列中篩選器的定義，同時傳回符合篩選器的清單的第一個／最後一個元素。

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**範例1:**

此運算式會傳回與版本為1.0的行動應用程式相關聯的第一個推播通知Token。

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

結果為&quot;token_1&quot;。

**範例2:**

此運算式會傳回與版本為1.0的行動應用程式相關聯的最後一個推播通知Token。

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

結果是&quot;token_2&quot;。

>[!NOTE]
>
>體驗事件是從Adobe Experience Platform擷取，依時間順序排列，因此：
>* **[!UICONTROL first]** 函式會傳回最近的事件
>* **[!UICONTROL last]** 函式會傳回最舊的函式。


**範例3:**

我們會檢查DMA ID的第一個（最近）Adobe Analytics事件（非零值）是否有等於602的值。

```
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**函式&quot;at(`<index>`)&quot;**

**[!UICONTROL at]**函式可讓您根據索引參考系列中的特定元素。
索引0是系列的第一個索引。

_`<listExpression>`.at(`<index>`)_

**範例:**

此運算式會傳回清單的第二個推播通知Token。

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

結果是&quot;token_2&quot;。