---
title: 關於進階使用案例
description: 進一步瞭解進階使用案例
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 5%

---


# 關於進階使用案例{#concept_vzy_ncy_w2b}

## 目的 {#purpose}

我們以一個叫馬爾頓的酒店品牌為例， 在他們的酒店裡，他們把信標設備放在了所有戰略區域附近：大堂、地板、餐廳、健身房、游泳池等。

>[!NOTE]
>
>在此使用案例中，我們使用Adobe Campaign Standard來傳送訊息。

在此使用案例中，我們將瞭解客戶在靠近特定信標時如何即時傳送個人化訊息給客戶。

首先，我們想在一個人進入馬爾頓酒店時，立即發送訊息。 我們只想在過去24小時內收到我們的任何通訊時傳送訊息。

然後，我們檢查兩個條件：

* 如果此人不是忠誠會員，我們會寄電子郵件給他以加入忠誠會籍優惠。
* 如果此人已是忠誠會員，我們會檢查他是否有房間訂房：
   * 如果他沒有，我們會以房費寄推播通知給他。
   * 如果他有，我們會寄歡迎推播通知給他。 如果他在接下來的6小時內進入餐廳，我們會給他發送一份推播通知，並在一餐時給他打折扣。

![](../assets/journeyuc2_29.png)

對於此使用案例，我們需要建立兩個事件(請參 [](../usecase/configuring-the-events.md)閱):

* 當客戶進入酒店時，將推送至系統的大堂信標事件。
* 當客戶進入餐廳時，會推送的餐廳信標事件。

我們需要設定兩個資料來源的連線(請參 [](../usecase/configuring-the-data-sources.md)閱):

* 內建的Adobe Experience Platform資料來源，可擷取我們兩個條件（忠誠會籍和上次聯絡日期）的資訊以及訊息個人化資訊。
* 該飯店訂房系統用以擷取該訂房狀態資訊。

## 先決條件 {#prerequisites}

針對我們的使用案例，我們設計了三個Adobe Campaign Standard交易訊息範本。 我們使用事件交易式訊息範本。 Refer to this [page](https://docs.adobe.com/content/help/zh-Hant/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign Standard已設定為傳送電子郵件和推播通知。

Experience Cloud ID是用來識別飯店訂房系統中客戶的金鑰。

當客戶在信標附近偵測到事件時，會從其行動電話傳送事件。 您需要設計行動應用程式，將事件從客戶的行動電話傳送至行動SDK。

「忠誠度成員」欄位是自訂欄位，已新增至XDM中，供我們特定組織ID使用。
