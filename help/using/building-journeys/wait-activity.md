---
title: 等待活動
description: 瞭解等待活動
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
source-git-commit: 92bd110c4c91c459c8074184bdb486733ab5f3d7
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 1%

---


# 等待活動{#section_rlm_nft_dgb}

如果要在路徑中執行下一個活動之前等待，可以使用活 **[!UICONTROL Wait]** 動。 它可讓您定義執行下一個活動的時間。 有四個選項可供使用：

* [持續時間](#duration)
* [固定日期](#fixed_date)
* [自訂](#custom)
* [電子郵件傳送時間最佳化](#email_send_time_optimization)

## 關於等待活動{#about_wait}

以下是當您同時使用數個等待時，等待的優先順序。 如果它們具有相同的時間配置和不同但重疊的條件，則位於上面的等待將是優先順序。 例如，第一次等待的條件是「成為女性」，而第二次等待的條件是「成為VIP」。 第一個等待活動將優先化

另請注意，如果兩個不同的等待同時進行，則無論其垂直位置如何，都會優先排列第一個發生的等待。 例如，如果1小時的等待高於30分鐘，而30分鐘的等待低於30分鐘，則30分鐘的等待將被處理。

如果要將等待限制在特定人口中，可以定義條件。

>[!NOTE]
>
>等待時間上限為30天。
>
>在測試模式中， **[!UICONTROL Wait time in test]** 參數可讓您定義每個等待活動的持續時間。 預設時間為 10 秒。這可確保您快速取得測試結果。 See [](../building-journeys/testing-the-journey.md)

## 持續等待{#duration}

選擇在執行下一個活動之前等待的持續時間。

![](../assets/journey55.png)

## 固定日期等待{#fixed_date}

選擇下一活動的執行日期。

![](../assets/journey56.png)

## 自訂等待{#custom}

此選項可讓您使用根據事件或資料來源產生的欄位的進階運算式，來定義自訂日期，例如2020年7月12日下午5點。 它不會讓您定義自訂持續時間，例如7天。 運算式編輯器中的運算式應提供dateTimeOnly格式。 請參閱[](../expression/expressionadvanced.md)。有關dateTimeOnly格式的詳細資訊，請參見 [](../expression/data-types.md)。

>[!NOTE]
>
>您可以運用dateTimeOnly運算式，或使用函式來轉換為dateTimeOnly。 例如：toDateTimeOnly(@{Event.offerOpened.activity.endTime})，事件中的欄位格式為2016-08-12T09:46:06。
>
>時 **區是** 您旅程的屬性。 因此，今天無法從介面直接指向完全ISO-8601時間戳記混合時間與時區偏移，例如2016-08-12T09:46:06.982-05。 請參閱[](../building-journeys/timezone-management.md)。

![](../assets/journey57.png)

## 電子郵件傳送時間最佳化{#email_send_time_optimization}

>[!CAUTION]
>
>電子郵件傳送時間最佳化功能僅適用於使用 [Adobe Experience Platform Data Connector的客戶](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html)。

此類等待會使用在Adobe Experience Platform中計算的分數。 分數會根據過去的行為，計算日後點按或開啟電子郵件的傾向。 請注意，計算分數的演算法需要一定數量的資料才能運作。 因此，當資料不足時，將會套用預設等待時間。 在出版時，將會通知您預設時間已套用。

>[!NOTE]
>
>您旅程的第一個事件必須有命名空間。
>
>此功能僅在活動後才可 **[!UICONTROL Email]** 用。 您必須擁有Adobe Campaign Standard。

1. 在欄位 **[!UICONTROL Amount of time]** 中，定義要考慮最佳化電子郵件傳送的小時數。
1. 在欄位中 **[!UICONTROL Optimization type]** ，選擇最佳化應增加點按還是開啟。
1. 在欄位 **[!UICONTROL Default time]** 中，定義預測性傳送時間分數不可用時的預設等待時間。

   >[!NOTE]
   >
   >請注意，傳送時間分數可能無法使用，因為沒有足夠的資料來執行計算。 在此情況下，您會在發佈時收到預設時間的通知。

![](../assets/journey57bis.png)
