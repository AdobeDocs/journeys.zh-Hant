---
product: adobe campaign
title: 關於進階使用案例
description: 深入瞭解歷程進階使用案例
feature: Journeys
role: User
level: Intermediate
exl-id: 43435aee-572d-4db2-88d5-6124ce074285
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 2%

---

# 關於進階使用案例{#concept_vzy_ncy_w2b}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_


## 目的 {#purpose}

以一個名為Marlton的飯店品牌為例。 他們在飯店中，在所有策略區域附近都放置了信標裝置：大廳、地板、餐廳、健身房、游泳池等。

>[!NOTE]
>
>在此使用案例中，我們使用Adobe Campaign Standard傳送訊息。

在此使用案例中，我們將瞭解當客戶靠近特定信標時，如何即時傳送個人化訊息給客戶。

首先，我們希望當某人進入瑪爾頓飯店時，能立即傳送訊息。 我們只想在人員過去24小時內未收到我們的任何通訊時傳送訊息。

我們接著會檢查兩個條件：

* 如果此人員不是忠誠會員，我們會傳送電子郵件給他們，以加入忠誠會員資格優惠方案。
* 如果此人已經是忠誠會員，我們會檢查他是否有訂房：
   * 如果沒有，我們會以房費傳送推播通知給對方。
   * 如果他這麼做，我們會傳送歡迎推播通知給他們。 如果他在6小時內進入餐廳，我們會傳送推播通知給他們，餐費可打折。

![](../assets/journeyuc2_29.png)

針對此使用案例，我們需要建立兩個事件（請參閱[此頁面](../usecase/configuring-the-events.md)）：

* 當客戶進入飯店時推送至系統的大廳信標事件。
* 當客戶進入餐廳時將推送的餐廳信標事件。

我們需要設定兩個資料來源的連線（請參閱[此頁面](../usecase/configuring-the-data-sources.md)）：

* 內建的Adobe Experience Platform資料來源，可擷取我們兩個條件（忠誠會員資格和上次聯絡日期）的資訊以及訊息個人化資訊。
* 飯店訂房系統，用來擷取訂房狀態資訊。

## 先決條件 {#prerequisites}

針對我們的使用案例，我們已設計三個Adobe Campaign Standard異動訊息範本。 我們正在使用事件異動訊息範本。 請參閱此[頁面](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=zh-Hant)。

Adobe Campaign Standard已設定為傳送電子郵件和推播通知。

Experience Cloud ID可當作在飯店訂房系統中識別客戶的金鑰。

當客戶在信標附近偵測到事件時，便會從客戶的行動電話傳送事件。 您需要設計行動應用程式，將事件從客戶的行動電話傳送至Mobile SDK。

「忠誠度會員」欄位是自訂欄位，已新增至XDM中的特定組織ID。
