---
product: adobe campaign
title: 關於Campaign v7/v8整合
description: 瞭解Campaign v7/v8整合
feature: Journeys
role: User
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 12%

---

# 使用 Adobe Campaign v7/v8 {#integrating-with-adobe-campaign-classic}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_


此整合適用於Adobe Campaign Classic v7 （從21.1版開始）和Adobe Campaign v8。 這可讓您使用 Adobe Campaign 交易型訊息功能來傳送電子郵件、推播通知及簡訊。

Journey Orchestration 與 Campaign 執行個體之間的連線在佈建時由 Adobe 設定。

此[區段](../usecase/campaign-classic-use-case.md)中呈現端對端使用案例。

對於已設定的每個動作，歷程設計器浮動視窗中都提供動作活動。 請參閱本[章節](../building-journeys/using-adobe-campaign-classic.md)。

## 重要備註

* 沒有訊息限制。 我們根據目前的Campaign SLA，將可傳送的訊息數量上限設為每小時50,000則以上。 因此，Journey Orchestration僅應用於單一使用案例（個別事件而非區段）。

* 您必須針對要使用的每個範本，在畫布上設定一個動作。 您需要在Journey Orchestration中，為您要從Adobe Campaign使用的每個範本設定一個動作。

* 建議您使用針對這項整合而託管的專用訊息中心執行個體，以避免影響您可能正在進行的任何其他行銷活動作業。 行銷伺服器可以是託管式或內部部署。 所需的組建版本是21.1版本候選版本或更新版本。

* 沒有驗證裝載或行銷活動訊息是否正確。

* 促銷活動動作不可與區段資格事件搭配使用。

## 先決條件

在Campaign中，您需要建立並發佈交易式訊息及其相關事件。 請參閱[Adobe Campaign檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=zh-Hant#transactional-messaging)。

您可以依照以下模式，建置與每則訊息相對應的JSON裝載。 之後，當您在Journey Orchestration中設定動作時，就會貼上此裝載（請參閱下文）

其範例如下：

```
{
    "channel": "email",
    "eventType": "welcome",
    "email": "example@adobe.com",
    "ctx": {
        "firstName": "John"
    }
}
```

* **頻道**：為您的Campaign交易範本定義的頻道
* **eventType**：您的行銷活動事件的內部名稱
* **ctx**：變數，根據您訊息中的個人化設定而定。

## 設定動作

在Journey Orchestration中，您需為每個異動訊息設定一個動作。 請依照下列步驟操作：

1. 建立新動作。 請參閱本[章節](../action/action.md)。
1. 輸入名稱和說明。
1. 在&#x200B;**動作型別**&#x200B;欄位中，選取&#x200B;**Adobe Campaign Classic**。
1. 按一下&#x200B;**裝載**&#x200B;欄位，然後貼上與Campaign訊息相對應的JSON裝載範例。 聯絡Adobe以取得此裝載。
1. 視您想要在歷程畫布上對應欄位，將不同的欄位調整為靜態或變數。 某些欄位，例如電子郵件地址和個人化欄位(ctx)的管道引數，您可能會想要定義為歷程內容中對應的變數。
1. 按一下&#x200B;**儲存**。

![](../assets/accintegration1.png)


