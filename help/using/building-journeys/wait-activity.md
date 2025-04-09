---
product: adobe campaign
title: 等待活動
description: 瞭解等待活動
feature: Journeys
role: User
level: Intermediate
exl-id: 819ff3c3-0e3e-4d86-b5d2-10c5b10d19e6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 7%

---

# 等待活動{#section_rlm_nft_dgb}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_



如果您想在執行路徑中的下一個活動之前先等待，可以使用&#x200B;**[!UICONTROL Wait]**&#x200B;活動。 這項功能可讓您定義執行下一個活動的時刻。有三個可用選項：

* [持續時間](#duration)
* [自訂](#custom)
  <!--* [Email send time optimization](#email_send_time_optimization)-->

## 關於等待活動{#about_wait}

以下說明當您同時使用數個等待時，等待的優先順序。 如果它們具有相同的時間設定和不同的重疊條件，則位於上方的等待將會是優先的等待。 例如，第一次等待的條件是「成為女性」，而第二次平行等待的條件是「成為VIP」。 第一個等待活動將排定優先順序。

另請注意，如果兩個不同的等待是平行的，則無論其垂直位置為何，都會優先處理第一個出現的等待。 例如，如果等待1小時以上，等待30分鐘以下，則在30分鐘後會處理30分鐘等待。

>[!NOTE]
>
>最長等待時間為30天。
>
>在測試模式中，**[!UICONTROL Wait time in test]**&#x200B;引數可讓您定義每個等待活動的持續時間。 預設時間為 10 秒。這將確保您能快速獲得測試結果。 檢視[此頁面](../building-journeys/testing-the-journey.md)

## 持續時間等待{#duration}

選取下一個活動執行前等待的持續時間。

![](../assets/journey55.png)

## 自訂等待{#custom}

此選項可讓您根據來自事件或資料來源的欄位，使用進階運算式來定義自訂日期，例如2020年7月12日下午5點。 它無法讓您定義自訂持續時間，例如7天。 運算式編輯器中的運算式應提供dateTimeOnly格式。 請參閱[此頁面](../expression/expressionadvanced.md)。 如需dateTimeOnly格式的詳細資訊，請參閱[此頁面](../expression/data-types.md)。

>[!NOTE]
>
>您可以利用dateTimeOnly運算式或使用函式來轉換為dateTimeOnly。 例如： toDateTimeOnly(@{Event.offerOpened.activity.endTime})，事件中的欄位格式為2016-08-12T09:46:06Z。
>
>您歷程的屬性中應該有&#x200B;**時區**。 因此，目前無法從介面直接指向完整的ISO-8601時間戳記混合時間和時區位移，例如2016-08-12T09:46:06.982-05。 請參閱[此頁面](../building-journeys/timezone-management.md)。

![](../assets/journey57.png)

<!--## Email send time optimization{#email_send_time_optimization}

>[!CAUTION]
>
>The email send time optimization capability is only available to customers who use the [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html).

This type of wait uses a score calculated in the Adobe Experience Platform. The score calculates the propensity to click or open an email in the future based on past behavior. Note that the algorithm calculating the score needs a certain amount of data to work. As a result, when it does not have enough data, the default wait time will apply. At publication time, you'll be notified that the default time applies.

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
