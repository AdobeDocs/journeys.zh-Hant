---
title: 關於簡單使用案例
description: 透過簡單的使用案例，進一步瞭解體驗
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
source-git-commit: 54b54a64ad2822eec96008ac4a2e16c208a4a3ab

---


# 關於簡單使用案例{#concept_grh_vby_w2b}

## 目的 {#purpose}

我們以一個叫馬爾頓的酒店品牌為例， 在他們的酒店裡，他們把信標設備放在了所有戰略區域附近：大堂、地板、餐廳、健身房、游泳池等。

在此使用案例中，我們將瞭解如何即時傳送個人化訊息給臨近Spa附近信標的人。

我們只想在某人是女性時傳送訊息。 消息必須在數秒內收到。

![](../assets/journeyuc1_16.png)

## 先決條件 {#prerequisites}

針對我們的使用案例，我們在Adobe Campaign Standard中設計了一個電子郵件交易訊息範本。 我們使用事件交易式訊息範本。 Refer to this [page](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign standard已設定為傳送電子郵件。

當在信標附近偵測到事件時，會從客戶的行動電話傳送。 您需要設計行動應用程式，將事件從客戶的行動電話傳送至行動SDK。