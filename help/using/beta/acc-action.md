---
product: adobe campaign
title: 關於Campaign Classic整合
description: 了解Campaign Classic整合
hide: true
hidefromtoc: true
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 2%

---

# 與 Adobe Campaign Classic 整合 {#integrating-with-adobe-campaign-classic}

此整合可讓您使用Adobe Campaign Classic交易訊息功能來傳送電子郵件、推播通知和簡訊。

Journey Orchestration與Campaign Classic例項之間的連線是在布建時由Adobe設定。

>[!CAUTION]
>
> 這項整合已發佈為私人測試版。 並非所有Journey Orchestration客戶都能使用。

## 重要附註

* 消息沒有限制。 根據我們目前的Campaign ClassicSLA，可將可以傳送的訊息數量限制為50,000/小時。 因此，Journey Orchestration僅應用於單一使用案例（個別事件，而非區段）。

* 您需要針對要使用的範本，在畫布上設定一個動作。

* 建議您使用為此整合托管的專用訊息中心執行個體，以避免影響您可能進行的任何其他Campaign Classic作業。 行銷伺服器可托管或內部部署。 所需的版本編號為21.1候選版本。

* 沒有驗證裝載或Campaign Classic消息正確。

* 您無法使用具有區段資格的Campaign Classic動作。

## 先決條件

在Campaign Classic中，您需要建立並發佈交易式訊息及其相關事件。 請參閱[Adobe Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging)。

請連絡Adobe，以取得與每則訊息對應的JSON裝載。 然後您會在Journey Orchestration中設定動作時貼上此裝載（請參閱下方）。

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

## 設定動作

在Journey Orchestration中，您需要為每個交易式訊息設定一個動作。 請依照下列步驟操作：

1. 建立新動作。 請參閱此[節](../action/action.md)。
1. 輸入名稱和說明。
1. 在&#x200B;**動作類型**&#x200B;欄位中，選取&#x200B;**Adobe Campaign Classic**。
1. 按一下&#x200B;**裝載**&#x200B;欄位，並貼上與Campaign Classic訊息對應的JSON裝載範例。 請聯絡Adobe以取得此裝載。
1. 調整不同的欄位。 某些欄位(例如管道參數和個人化欄位(ctx))必須定義為變數。
1. 按一下「**儲存**」。

![](../assets/accintegration1.png)

對於已設定的每個動作，歷程設計器浮動視窗中都會提供動作活動。

## 在歷程中新增訊息

1. 從事件開始，設計您的歷程。 請參閱此[節](../building-journeys/journey.md)。
1. 在浮動視窗的&#x200B;**Action**&#x200B;區段中，選取Campaign Classic動作並將其新增至您的歷程。
1. 在&#x200B;**動作參數**&#x200B;中，會顯示訊息裝載中預期的所有欄位。 您需要將每個欄位對應至您要使用的欄位，不論是來自事件或來自資料來源。 這類似於自訂動作。 請參閱此[節](../building-journeys/using-custom-actions.md)。

![](../assets/accintegration2.png)
