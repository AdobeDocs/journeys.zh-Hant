---
product: adobe campaign
solution: Journey Orchestration
title: 與外部系統整合
description: 瞭解整合外部系統時的最佳實務
feature: Journeys
role: User
level: Beginner
exl-id: e39218bd-fa6e-443f-9843-92b7a07070fa
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 5%

---

# 與外部系統整合 {#external-systems}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_



本頁介紹Journey Orchestration在整合外部系統時提供的各種護欄，以及最佳實務：如何使用上限API最佳化外部系統的保護、如何設定歷程逾時，以及重試如何運作。

Journey Orchestration可讓您透過自訂資料來源和自訂動作來設定與外部系統的連線。 舉例來說，這可讓您利用來自外部訂房系統的資料，豐富您的歷程，或是使用Epsilon或Facebook等協力廠商系統傳送訊息。

整合外部系統時，您可能會遇到幾個問題：系統可能緩慢、停止回應，或是可能無法處理較大的磁碟區。 Journey Orchestration提供數個護欄，可保護您的系統避免過載。

所有外部系統的效能都不同。 您需要調整設定以符合使用案例。

Journey Orchestration執行外部API呼叫時，技術護欄會依照以下方式執行：

1. 套用上限規則：如果達到最大速率，則會捨棄剩餘的呼叫。

2. 逾時並重試：如果已履行上限規則，Journey Orchestration會嘗試執行呼叫，直到逾時期間結束時為止。

## 頻率上限{#capping}

內建的上限API提供上游技術護欄，可協助保護您的外部系統。

對於外部資料來源，每秒呼叫數上限設為15。 如果通話次數超過每秒15次，則會捨棄剩餘的通話。 您可以提高私人外部資料來源的此限制。 請聯絡Adobe以將此端點加入允許清單中。 公開外部資料來源無法執行此操作。

對於自訂動作，您需要評估外部API的容量。 例如，如果Journey Optimizer每秒傳送1000個呼叫，而您的系統僅支援每秒100個呼叫，則您需要定義上限規則，讓系統不會飽和。

上限規則是在特定端點（呼叫的URL）的沙箱層級定義。 在執行階段，Journey Orchestration會驗證是否已定義上限規則，並在呼叫該端點期間套用定義的速率。 如果呼叫數超過定義的速率，則會捨棄剩餘的呼叫，並在報表中計為錯誤。

上限規則專用於一個端點，但沙箱的所有歷程是全域的。 這表示沙箱的所有歷程會共用限定槽。

例如，假設您已為外部系統定義每秒100次呼叫的上限規則。 10 個不同歷程的自訂動作會呼叫您的系統。 如果某個歷程每秒接聽200次呼叫，就會使用可用的100個位置並捨棄剩餘的100個位置。 由於已超過最大速率，其他 9 個歷程將沒有任何插槽。 此詳細程度有助於保護外部系統免於過載及損毀。

若要進一步瞭解上限API以及如何設定上限規則，請參閱[此頁面](../api/capping.md)。

## 逾時和重試{#timeout}

如果符合上限規則，則會套用逾時規則。

在每個歷程中，您可以定義逾時持續時間。 這可讓您設定呼叫外部系統時的最長持續時間。 逾時期間是在歷程的屬性中設定。 請參見[此頁面](../building-journeys/changing-properties.md#timeout_and_error)。

此逾時對於所有外部呼叫（自訂動作和自訂資料來源中的外部API呼叫）都是全域的。 預設會設為5秒。

在定義的逾時期間，Journey Orchestration會嘗試呼叫外部系統。 在第一次呼叫後，最多可以執行三次重試，直到逾時持續時間結束為止。 無法變更重試次數。

每個重試使用一個插槽。 如果您有每秒100次呼叫的上限，且您的每個呼叫需要重試兩次，則速率會降至每秒30次呼叫（每個呼叫使用3個槽：第一次呼叫和兩次重試）。

逾時期間值取決於使用案例。 如果您想要快速傳送訊息（例如，當使用者端進入商店時），則您不想設定漫長的逾時。 此外，逾時時間越長，放入佇列中的專案就越多。 這可能會大幅影響效能。 如果Journey Orchestration每秒執行1000次呼叫，保留5或15秒的資料會迅速讓系統不知所措。

以逾時5秒為例。

* 第一個呼叫持續少於5秒：呼叫成功，不會執行重試。
* 第一個呼叫會持續更長的5秒：呼叫已取消，而且不會重試。 在報表中會計為逾時錯誤。
* 第一次呼叫在2秒後失敗（外部系統傳回錯誤）：如果有上限插槽，重試還剩3秒。
   * 如果在5秒結束前三次重試其中一次成功，則會執行呼叫，而且不會發生錯誤。
   * 如果在重試期間到達逾時持續時間的結尾，則會取消呼叫，並在報表中計為逾時錯誤。

## 常見問題{#faq}

**如何設定上限規則？ 是否有預設的上限規則？**

依預設，沒有上限規則。 上限規則是使用上限API，在特定端點（呼叫的URL）的沙箱層級定義。 請參閱[此章節](../about/external-systems.md#capping)和[此頁面](../api/capping.md)。

**執行多少次重試？ 我可以變更重試次數或定義兩次重試之間的最短等待時間嗎？**

對於指定的呼叫，在第一次呼叫之後最多可以執行三次重試，直到逾時持續時間結束為止。 無法變更重試次數和每次重試之間的時間。 請參閱[本節](../about/external-systems.md#timeout)。

**我可以在哪裡設定逾時？ 有最大值嗎？**

在每個歷程中，您可以定義逾時持續時間。 逾時期間是在歷程的屬性中設定。 逾時持續時間必須介於1秒到30秒之間。 請參閱[此章節](../about/external-systems.md#timeout)和[此頁面](../building-journeys/changing-properties.md#timeout_and_error)。
