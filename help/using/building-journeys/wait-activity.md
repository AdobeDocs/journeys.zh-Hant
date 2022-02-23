---
product: adobe campaign
title: 等待活動
description: 瞭解等待活動
feature: Journeys
role: User
level: Intermediate
exl-id: 819ff3c3-0e3e-4d86-b5d2-10c5b10d19e6
source-git-commit: bdc9ac3f54fae1dfd6f24a54a2687a0834f69c36
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 4%

---

# 等待活動{#section_rlm_nft_dgb}

如果要在執行路徑中的下一個活動之前等待，可以使用 **[!UICONTROL Wait]** 的子菜單。 它允許您定義執行下一個活動的時間。 有三種選擇：

* [持續時間](#duration)
* [固定日期](#fixed_date)
* [自訂](#custom)

<!--* [Email send time optimization](#email_send_time_optimization)-->

## 關於等待活動{#about_wait}

以下是並行使用多個等待時如何排定優先順序。 如果它們具有相同的時間配置和不同但重疊的條件，則位於上方的等待將是按優先順序排序的等待。 例如，第一次等待的條件是「為女人」，而第二次並行等待的條件是「為VIP女人」。 第一個等待活動將按優先順序排列。

另請注意，如果兩個不同的等待並行，則無論其垂直位置如何，都會優先排定第一個出現的等待。 例如，如果1小時的等待時間高於30分鐘的等待時間，則30分鐘後將處理30分鐘的等待時間。

>[!NOTE]
>
>最大等待持續時間為30天。
>
>在test模式下， **[!UICONTROL Wait time in test]** 參數允許您定義每個等待活動將持續的時間。 預設時間為 10 秒。這將確保您快速獲得test結果。 請參閱 [此頁](../building-journeys/testing-the-journey.md)

## 持續時間等待{#duration}

選擇在執行下一活動之前等待的持續時間。

![](../assets/journey55.png)

## 固定日期等待{#fixed_date}

選擇下一活動的執行日期。

![](../assets/journey56.png)

## 自定義等待{#custom}

此選項允許您使用基於來自事件或資料源的欄位的高級表達式來定義自定義日期，例如2020年7月12日下午5點。 它不允許您定義自定義持續時間，例如7天。 表達式編輯器中的表達式應提供dateTimeOnly格式。 請參閱[此頁面](../expression/expressionadvanced.md)。有關dateTimeOnly格式的詳細資訊，請參見 [此頁](../expression/data-types.md)。

>[!NOTE]
>
>可以利用dateTimeOnly表達式或使用函式轉換為dateTimeOnly。 例如：toDateTimeOnly(@{Event.offerOpened.activity.endTime})，事件中的欄位為2016-08-12T09:46:06Z。
>
>的 **時區** 在你旅程的屬性中。 因此，目前無法從介面直接指向完全ISO-8601時間戳混合時間和時區偏移，如2016-08-12T09:46:06.982-05。 請參閱[此頁面](../building-journeys/timezone-management.md)。

![](../assets/journey57.png)

<!--## Email send time optimization{#email_send_time_optimization}

>[!CAUTION]
>
>The email send time optimization capability is only available to customers who use the [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html).

This type of wait uses a score calculated in the Adobe Experience Platform. The score calculates the propensity to click or open an email in the future based on past behavior. Note that the algorithm calculating the score needs a certain amount of data to work. As a result, when it does not have enough data, the default wait time will apply. At publication time, you’ll be notified that the default time applies.

>[!NOTE]
>
>The first event of your journey must have a namespace.
>
>This capability is only available after an **[!UICONTROL Email]** activity. You need to have Adobe Campaign Standard.

1. In the **[!UICONTROL Amount of time]** field, define the number of hours to consider to optimize email sending.
1. In the **[!UICONTROL Optimization type]** field, choose if the optimization should increase clicks or opens.
1. In the **[!UICONTROL Default time]** field, define the default time to wait if the predictive send time score is not available.

    >[!NOTE]
    >
    >Note that the send time score can be unavailable because there is not enough data to perform the calculation. In this case, you will be informed, at publication time, that the default time applies.

![](../assets/journey57bis.png)-->
