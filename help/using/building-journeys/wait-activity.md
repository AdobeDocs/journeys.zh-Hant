---
product: adobe campaign
title: 等待活動
description: 了解等候活動
feature: 歷程
role: User
level: Intermediate
exl-id: 819ff3c3-0e3e-4d86-b5d2-10c5b10d19e6
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 4%

---

# 等待活動{#section_rlm_nft_dgb}

如果要在路徑中執行下一個活動之前等待，則可以使用&#x200B;**[!UICONTROL Wait]**&#x200B;活動。 它可讓您定義下一個活動的執行時間。 有三個可用選項：

* [持續時間](#duration)
* [固定日期](#fixed_date)
* [自訂](#custom)

<!--* [Email send time optimization](#email_send_time_optimization)-->

## 關於等待活動{#about_wait}

以下是當您同時使用數個等待時，會如何排定優先順序的等待。 如果它們具有相同的時間配置和不同但重疊的條件，則位於上方的等待將是優先順序。 例如，第一次等待的條件是「為女性」，而第二次同時等待的條件是「為VIP」。 第一個等待活動將優先

另請注意，如果兩個不同的等待並行，則無論其垂直位置為何，發生在前面的等待都會優先順序。 例如，如果1小時等候高於30分鐘等候低於，30分鐘後，將會處理30分鐘等候。

如果要限制等候至特定母體，可以定義條件。

>[!NOTE]
>
>等待時間上限為30天。
>
>在測試模式中，**[!UICONTROL Wait time in test]**&#x200B;參數可讓您定義每個等待活動的持續時間。 預設時間為 10 秒。這可確保您快速取得測試結果。 請參閱[此頁面](../building-journeys/testing-the-journey.md)

## 持續等待{#duration}

選取下一個活動執行之前等待的持續時間。

![](../assets/journey55.png)

## 固定日期等待{#fixed_date}

選取下一個活動的執行日期。

![](../assets/journey56.png)

## 自訂等待{#custom}

此選項可讓您根據來自事件或資料來源的欄位，使用進階運算式來定義自訂日期，例如2020年7月12日下午5點。 它不會讓您定義自訂持續時間，例如7天。 運算式編輯器中的運算式應提供dateTimeOnly格式。 請參閱[此頁面](../expression/expressionadvanced.md)。如需dateTimeOnly格式的詳細資訊，請參閱[此頁面](../expression/data-types.md)。

>[!NOTE]
>
>您可以運用dateTimeOnly運算式，或使用函式來轉換為dateTimeOnly。 例如：toDateTimeOnly(@{Event.offerOpened.activity.endTime})，事件中的欄位為2016-08-12T09:46:06Z格式。
>
>歷程的屬性中會預期&#x200B;**時區**。 因此，今天無法從介面直接指向完整的ISO-8601時間戳，混合時間和時區偏移，如2016-08-12T09:46:06.982-05。 請參閱[此頁面](../building-journeys/timezone-management.md)。

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
