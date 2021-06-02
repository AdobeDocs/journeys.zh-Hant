---
product: adobe campaign
title: 關於簡單使用案例
description: 深入了解歷程的簡單使用案例
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 11858c7a-fdb3-43a4-af28-0d5c23fa2468
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 12%

---

# 關於簡單使用案例{#concept_grh_vby_w2b}

## 用途 {#purpose}

我們舉一個名為馬爾頓的酒店品牌為例。 在他們的酒店裡，他們在所有戰略區域附近都部署了信標設備：大廳、地板、餐廳、健身房、游泳池等

在此使用案例中，我們將了解如何即時傳送個人化訊息給臨近Spa附近信標的人員。

我們只想在人是女人時才發資訊。 必須在秒內收到消息。

![](../assets/journeyuc1_16.png)

## 先決條件 {#prerequisites}

針對我們的使用案例，我們在Adobe Campaign Standard中設計了一個電子郵件交易式訊息範本。 我們使用事件交易式訊息範本。 請參閱此[page](https://docs.adobe.com/content/help/zh-Hant/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)。

Adobe Campaign Standard已設定為傳送電子郵件。

當在信標附近偵測到事件時，會從客戶的行動電話傳送這些事件。 您需要設計行動應用程式，將事件從客戶的行動電話傳送至行動SDK。
