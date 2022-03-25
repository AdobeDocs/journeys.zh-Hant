---
product: adobe campaign
title: 關於簡單使用案例
description: 更深入地瞭解旅程的簡單使用案例
feature: Journeys
role: User
level: Intermediate
exl-id: 11858c7a-fdb3-43a4-af28-0d5c23fa2468
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 11%

---

# 關於簡單使用案例{#concept_grh_vby_w2b}

## 用途 {#purpose}

我們舉一個名為馬爾頓的酒店品牌為例。 在酒店裡，他們把信標設備定位在所有戰略區域附近：大堂、地板、餐廳、健身房、游泳池等。

在此使用案例中，我們將瞭解如何即時地向在spa附近的信標旁邊行走的人發送個性化資訊。

我們只想在某人是女人時發送資訊。 必須在幾秒內接收消息。

![](../assets/journeyuc1_16.png)

## 先決條件 {#prerequisites}

為了使用案例，我們在Adobe Campaign Standard設計了一個電子郵件事務性消息傳遞模板。 我們使用事件事務性消息傳遞模板。 請參閱此 [頁](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=zh-Hant)。

Adobe Campaign Standard配置為發送電子郵件。

當在信標附近檢測到事件時，從客戶的行動電話發送事件。 您需要設計移動應用程式，以便將事件從客戶的手機發送到MobileSDK。
