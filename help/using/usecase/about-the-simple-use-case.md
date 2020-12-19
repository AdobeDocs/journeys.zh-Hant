---
product: adobe campaign
solution: Journey Orchestration
title: 關於簡單使用案例
description: 透過簡單的使用案例，進一步瞭解體驗
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 12%

---


# 關於簡單使用案例{#concept_grh_vby_w2b}

## 用途{#purpose}

我們以一個叫馬爾頓的酒店品牌為例， 在他們的酒店裡，他們把信標設備放在了所有戰略區域附近：大堂、地板、餐廳、健身房、游泳池等。

在此使用案例中，我們將瞭解如何即時傳送個人化訊息給臨近Spa附近信標的人。

我們只想在某人是女性時傳送訊息。 消息必須在數秒內收到。

![](../assets/journeyuc1_16.png)

## 先決條件 {#prerequisites}

針對我們的使用案例，我們在Adobe Campaign Standard中設計了一個電子郵件交易訊息範本。 我們使用事件交易式訊息範本。 請參閱此[頁](https://docs.adobe.com/content/help/zh-Hant/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)。

Adobe Campaign Standard已設定為傳送電子郵件。

當在信標附近偵測到事件時，會從客戶的行動電話傳送。 您需要設計行動應用程式，將事件從客戶的行動電話傳送至行動SDK。