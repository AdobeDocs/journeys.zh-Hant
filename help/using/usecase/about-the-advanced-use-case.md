---
product: adobe campaign
title: 關於進階使用案例
description: 深入了解歷程進階使用案例
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 43435aee-572d-4db2-88d5-6124ce074285
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 5%

---

# 關於進階使用案例{#concept_vzy_ncy_w2b}

## 用途 {#purpose}

我們舉一個名為馬爾頓的酒店品牌為例。 在他們的酒店裡，他們在所有戰略區域附近都部署了信標設備：大廳、地板、餐廳、健身房、游泳池等

>[!NOTE]
>
>在此使用案例中，我們會使用Adobe Campaign Standard來傳送訊息。

在此使用案例中，我們將說明當客戶靠近特定信標時，如何即時傳送個人化訊息給客戶。

首先，我們想在有人進入馬爾頓酒店時立即發送資訊。 我們只想在過去24小時內收到我們的任何通信時發送消息。

然後，我們檢查兩個條件：

* 如果此人不是忠誠會員，我們會傳送電子郵件給他，加入忠誠會員優惠。
* 如果此人已是忠誠會員，我們會檢查他是否有客房預訂：
   * 如果他沒有，我們會以房費向他發送推播通知。
   * 如果他有，我們會傳送歡迎推播通知給他。 如果他在接下來的6小時內進入餐廳，我們會向他發送一條推播通知，並在一餐中打折。

![](../assets/journeyuc2_29.png)

對於此使用案例，我們需要建立兩個事件（請參閱[此頁面](../usecase/configuring-the-events.md)）:

* 當客戶進入酒店時，會推送至系統的大堂信標事件。
* 當客戶進入餐廳時，會推播的餐廳信標事件。

我們需要配置到兩個資料源的連接（請參閱[此頁](../usecase/configuring-the-data-sources.md)）:

* 內建的Adobe Experience Platform資料來源，可擷取我們兩個條件（忠誠會籍和上次聯絡日期）的資訊，以及訊息個人化資訊。
* 酒店預訂系統，用於檢索預訂狀態資訊。

## 先決條件 {#prerequisites}

針對我們的使用案例，我們設計了三個Adobe Campaign Standard交易式訊息範本。 我們使用事件交易式訊息範本。 請參閱此[page](https://docs.adobe.com/content/help/zh-Hant/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)。

Adobe Campaign Standard已設定為傳送電子郵件和推播通知。

Experience CloudID會作為識別酒店訂房系統中客戶的金鑰。

當客戶在信標附近偵測到事件時，會從其行動電話傳送事件。 您需要設計行動應用程式，將事件從客戶的行動電話傳送至行動SDK。

「忠誠會員」欄位是自訂欄位，已針對特定組織ID在XDM中新增。
