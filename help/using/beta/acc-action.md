---
product: adobe campaign
solution: Journey Orchestration
title: 關於Campaign Classic整合
description: 瞭解Campaign Classic整合
hide: true
hidefromtoc: true
translation-type: tm+mt
source-git-commit: 937b7235d41fe7f0395e303736974e32eea8558f
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 0%

---


# 與Adobe Campaign Classic整合{#integrating-with-adobe-campaign-classic}

此項整合可讓您使用Adobe Campaign Classic交易訊息功能來傳送電子郵件、推播通知和簡訊。

Journey Orchestration實例和Campaign Classic實例之間的連接是通過Adobe在設定時設定的。

>[!CAUTION]
>
> 此整合會以私人測試版發佈。 並非所有Journey Orchestration客戶都能使用。

## 重要附註

* 消息沒有調節。 根據我們當前的Campaign ClassicSLA，我們將可以發送的消息數限制為每小時50,000條。 因此，「歷程協調」只應用於單一使用案例（個別事件，而非細分）。

* 您必須在畫布上，針對您想使用的範本設定一個動作。

* 我們建議您使用為此整合托管的專用消息中心實例，以避免影響您正在進行的任何其他Campaign Classic操作。 行銷伺服器可由主機代管或內部部署。 所需的組建版本是21.1版候選版。

* 沒有驗證裝載或Campaign Classic消息是否正確。

* 您不能將Campaign Classic動作與區段資格搭配使用。

## 必要條件

在Campaign Classic中，您需要建立和發佈事務性消息及其關聯事件。 請參閱[Adobe Campaign Classic文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging)。

連絡Adobe以取得每個訊息對應的JSON裝載。 然後，在Journey Orchestration中設定動作時，您會貼上此裝載（請參閱下面）。

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

在Journey Orchestration中，您需要為每個事務性消息配置一個操作。 請遵循下列步驟：

1. 建立新動作。 請參閱此[節](../action/action.md)。
1. 輸入名稱和說明。
1. 在&#x200B;**Action type**&#x200B;欄位中，選擇&#x200B;**Adobe Campaign Classic**。
1. 在&#x200B;**Payload**&#x200B;欄位中按一下，並貼上與Campaign Classic訊息對應的JSON裝載範例。 請聯絡Adobe以取得此裝載。
1. 調整不同欄位。 某些欄位，例如頻道參數和個人化欄位(ctx)，必須定義為變數。
1. 按一下&#x200B;**保存**。

![](../assets/accintegration1.png)

對於每個設定的動作，歷程設計工具浮動視窗中都會提供動作活動。

## 在歷程中新增訊息

1. 從活動開始，設計您的旅程。 請參閱此[節](../building-journeys/journey.md)。
1. 在浮動視窗的&#x200B;**Action**&#x200B;區段中，選取Campaign Classic動作並將它新增至歷程中。
1. 在&#x200B;**Action參數**&#x200B;中，將顯示消息裝載中預期的所有欄位。 您需要將每個欄位對應至您要使用的欄位，不論是來自事件或來自資料來源。 這類似於自訂動作。 請參閱此[節](../building-journeys/using-custom-actions.md)。

![](../assets/accintegration2.png)

