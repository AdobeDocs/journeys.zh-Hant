---
title: 關於歷程協調
description: 進一步瞭解歷程協調
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27

---


# 關於歷程協調{#concept_nd3_mqt_52b}

運用儲存在事件或資料來源中的情境資料，建立即時協調使用案例。

Journey Orchestration是與Experience platform整合的應用程式服務。

![](../assets/journeydiagram.png)

Journey Orchestration可讓您即時協調，並運用來自活動的情境式資料、來自Adobe Experience Platform的資訊或來自協力廠商API服務的資料。 如果您使用協力廠商系統來傳送訊息，可以設定自訂動作。 如果您有Adobe Campaign Standard，您就可以使用Adobe Campaign Standard的「交易訊息」功能來傳送電子郵件、推播通 [知和簡訊](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)。

在事件設定標籤中，技術使 **用者設定** 「歷程」中預期的事件。 傳入事件的資料會依照Adobe Experience Data Model(XDM)進行標準化。 事件來自串流擷取API，用於驗證和未驗證的事件（例如Adobe Mobile SDK事件）。

在資料源配置頁籤中，技術用 **戶配置** :

* 旅程設計人員中Adobe Experience platform中公開的不同欄位，以用於條件建立和個人化目的。
* 您在歷程設計人員中運用的其他自訂資料來源。 自訂資料來源是Journey Orchestration與協力廠商系統或服務之間透過API的連線。 您可以連接第三方系統，例如忠誠度系統。 例如，協力廠商服務可以是氣象API。

有了歷程設計人員，商 **業使用者** ，就可輕鬆拖放參加項目事件、新增條件並指定要執行的動作。

然後，您可以根據下列項目建立條件：

* 時間
* 來自事件裝載的資料
* 來自資料來源的資訊：即時客戶個人檔案資料來源或自訂資料來源

您可以使用分割條件，將人們引導至不同的旅程。

然後，您可以使用動作活動，透過協力廠商系統傳送訊息。 如果您有Adobe Campaign Standard，請傳送即時個人化的簡訊、推播通知或電子郵件。

由於「歷程協調」是多步驟的，您可以建立進階的藍本。 例如，在第一個事件和動作之後，您可以拖曳其他事件。 然後，您可以新增第二個動作、放置等待活動以等待一段時間、新增分割條件以將訪客推送至兩個不同的路徑，然後傳送不同的訊息。

>[!NOTE]
>
>本檔案會經常更新，以反映產品的最近變更。 不過，有些螢幕擷取畫面可能會與產品的介面稍有不同。

