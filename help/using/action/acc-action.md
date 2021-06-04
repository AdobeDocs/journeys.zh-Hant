---
product: adobe campaign
title: 關於Campaign Classic整合
description: 了解Campaign Classic整合
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: c17808a4cae7ebbd1129f6b28ad2ea945098f826
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 0%

---

# 使用Adobe Campaign Classic {#integrating-with-adobe-campaign-classic}

此整合可讓您使用Adobe Campaign Classic交易訊息功能來傳送電子郵件、推播通知和簡訊。

Journey Orchestration與Campaign Classic例項之間的連線是在布建時由Adobe設定。

此[section](../usecase/campaign-classic-use-case.md)中顯示了端到端使用案例。

對於已設定的每個動作，歷程設計器浮動視窗中都會提供動作活動。 請參閱此[節](../building-journeys/using-adobe-campaign-classic.md)。

## 重要附註

* 消息沒有限制。 根據我們目前的Campaign ClassicSLA，可將可以傳送的訊息數量限制為50,000/小時。 因此，Journey Orchestration僅應用於單一使用案例（個別事件，而非區段）。

* 您需要針對要使用的範本，在畫布上設定一個動作。 您需要針對要從Adobe Campaign Classic使用的每個範本，在Journey Orchestration中設定一個動作。

* 建議您使用為此整合托管的專用訊息中心執行個體，以避免影響您可能進行的任何其他Campaign Classic作業。 行銷伺服器可托管或內部部署。 所需的版本編號為21.1 Release Candiate或更高版本。

* 沒有驗證裝載或Campaign Classic消息正確。

* 您無法將Campaign Classic動作與區段資格事件搭配使用。

## 先決條件

在Campaign Classic中，您需要建立並發佈交易式訊息及其相關事件。 請參閱[Adobe Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging)。

您可以依照下列模式，建立與每個訊息對應的JSON裝載。 接著，您會在Journey Orchestration中設定動作時貼上此裝載（請參閱下方）

以下是範例：

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

* **管道**:為您的Campaign Classic交易式範本定義的管道
* **eventType**:您的Campaign Classic事件的內部名稱
* **ctx**:變數。

## 設定動作

在Journey Orchestration中，您需要為每個交易式訊息設定一個動作。 請依照下列步驟操作：

1. 建立新動作。 請參閱此[節](../action/action.md)。
1. 輸入名稱和說明。
1. 在&#x200B;**動作類型**&#x200B;欄位中，選取&#x200B;**Adobe Campaign Classic**。
1. 按一下&#x200B;**裝載**&#x200B;欄位，並貼上與Campaign Classic訊息對應的JSON裝載範例。 請聯絡Adobe以取得此裝載。
1. 視您要在歷程畫布上對應不同欄位，將其調整為靜態或變數。 某些欄位(例如電子郵件地址和個人化欄位(ctx)的管道參數)，您可能會想要定義為要在歷程內容中對應的變數。
1. 按一下「**儲存**」。

![](../assets/accintegration1.png)


