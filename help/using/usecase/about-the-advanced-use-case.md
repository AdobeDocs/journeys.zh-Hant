---
product: adobe campaign
title: 關於進階使用案例
description: 更深入地瞭解高級使用案例
feature: Journeys
role: User
level: Intermediate
exl-id: 43435aee-572d-4db2-88d5-6124ce074285
source-git-commit: 579e5a0dbdc11369248c2683c399b090130a7262
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 4%

---

# 關於進階使用案例{#concept_vzy_ncy_w2b}

## 用途 {#purpose}

我們舉一個名為馬爾頓的酒店品牌為例。 在酒店裡，他們把信標設備定位在所有戰略區域附近：大堂、地板、餐廳、健身房、游泳池等。

>[!NOTE]
>
>在此使用情況下，我們使用Adobe Campaign Standard發送消息。

在此使用案例中，我們將瞭解如何在客戶走近特定信標時即時向客戶發送個性化消息。

首先，我們想在一個人進入馬爾頓酒店後立即發送資訊。 我們只想在過去24小時內收到我們的任何來文時發送消息。

然後，我們檢查兩個條件：

* 如果此人不是會員，我們會向他們發送電子郵件以加入會員資格。
* 如果此人已是忠誠會員，我們將檢查他是否有房間預訂：
   * 如果他沒有，我們會給他們發一份按房費的推送通知。
   * 如果他有，我們會向他們發送歡迎推送通知。 如果他在6小時內進入餐廳，我們會給他們發送一份推送通知，並在一頓飯上打折。

![](../assets/journeyuc2_29.png)

對於此用例，我們需要建立兩個事件(請參見 [此頁](../usecase/configuring-the-events.md)):

* 當客戶進入酒店時，將推送到系統的大堂信標事件。
* 當客戶進入餐廳時將推送的餐廳信標事件。

我們需要配置到兩個資料源的連接(請參見 [此頁](../usecase/configuring-the-data-sources.md)):

* 內置的Adobe Experience Platform資料源，用於檢索我們兩個條件（會員資格和最後聯繫日期）的資訊以及消息個性化資訊。
* 酒店預訂系統，用於檢索預訂狀態資訊。

## 先決條件 {#prerequisites}

針對我們的使用案例，我們設計了三個Adobe Campaign Standard事務性消息傳遞模板。 我們使用事件事務性消息傳遞模板。 請參閱此 [頁](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=zh-Hant)。

Adobe Campaign Standard配置為發送電子郵件和推送通知。

Experience CloudID用作在酒店預訂系統中標識客戶的密鑰。

當在信標附近檢測到事件時，從客戶的行動電話發送事件。 您需要設計移動應用程式，以便將事件從客戶的手機發送到MobileSDK。

「會員」成員欄位是自定義欄位，已添加到XDM中，用於特定組織ID。
