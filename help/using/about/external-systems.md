---
product: adobe campaign
solution: Journey Orchestration
title: 與外部系統整合
description: 了解整合外部系統時的最佳實務
feature: Journeys
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: a25ff95e0b74d3a0693310179670c7fe7b0de51c
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---

# 與外部系統整合{#external-systems}

本頁介紹整合外部系統時由Journey Orchestration提供的不同護欄，以及最佳實務：如何使用上限API最佳化對外部系統的保護、如何設定歷程逾時，以及重試的運作方式。

Journey Orchestration可讓您透過自訂資料來源和自訂動作，設定與外部系統的連線。 舉例來說，這可讓您透過來自外部訂房系統的資料來豐富您的歷程，或使用Epsilon或Facebook等協力廠商系統來傳送訊息。

在整合外部系統時，您可能會遇到幾個問題，系統可能會變慢，可能會停止響應，或者它可能無法處理大容量。 Journey Orchestration提供數個護欄，以保護您的系統不會過度載入。

所有外部系統在效能上都不同。 您需要根據每個使用案例調整設定。

當Journey Orchestration執行對外部API的呼叫時，技術護欄會執行如下：

1. 上限設定：套用上限規則
2. 超時並重試：

## 限定

內建的上限API提供上游技術護欄，以協助保護您的外部系統。 您必須事先評估外部API的容量。 例如，如果Journey Orchestration每秒傳送1000次呼叫，而您的系統每秒只能支援100次呼叫，則您需要定義上限規則，使系統不會飽和。

限定規則是在特定端點的沙箱層級定義（稱為URL）。 在執行階段，Journey Orchestration會驗證是否定義了上限規則，並在呼叫該端點期間套用所定義的速率。 如果呼叫數超過定義的速率，則會捨棄剩餘的呼叫。

上限規則是一個端點專屬的，但是對沙箱的所有歷程為全域。 這表示呼叫位置會在沙箱的所有歷程之間共用。 例如，假設您的外部系統已定義每秒100次呼叫的上限，且這是由10個不同歷程中的自訂動作呼叫。 如果一個歷程每秒收到200個呼叫，將會保留100個槽可用，並捨棄剩餘的100個槽。 由於已超出最大比率，其他9個歷程將沒有任何可用的槽。 此粒度有助於保護外部系統免受過載和崩潰的影響。

由於上限限制而捨棄的呼叫在報表中會計為錯誤。

若要了解如何設定上限規則，請參閱[本頁面](../api/timezone-management.md)。

## 逾時和重試

Ensuite -> timeout defini, et qui definir le temps maximal qu&#39;on aloue a lappl a u sys externe. 《魔戒》，關於魔咒的。 在「Fait un appl」上，「s l&#39;appl dure moinre longtemps que le timeout ca marche」，「s i plus longtemps on voit ca comme due timeout error」， et coté reporting compabilisé comme due errur。 請重試，(apper sur 500 ou autre)。 最多3次重試，可配置pas。 SI可執行逾時(par exemple 2 essa, mais depasse le timeout)。 必要的話。 逾時期間max qu&#39;on alloue a apple et aux retires為錯誤。

