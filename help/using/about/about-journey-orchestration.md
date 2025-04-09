---
product: adobe campaign
title: 關於 Journey Orchestration
description: 進一步瞭解 Journey Orchestration
feature: Journeys
role: User
level: Beginner
exl-id: 430bac3a-06da-45a8-af90-1dcd1504d532
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 89%

---

# 關於 [!DNL Journey Orchestration]{#concept_nd3_mqt_52b}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_


運用儲存在事件或資料來源中的內容資料，建立即時協調使用案例。

[!DNL Journey Orchestration] 是與 Adobe Experience Platform 整合的應用程式服務。

[!DNL Journey Orchestration] 能以事件中的情境資料、Adobe Experience Platform 的資訊或來自協力廠商 API 服務的資料，進行即時協調。如果您使用協力廠商系統來傳送訊息，則可設定自訂動作。如果您有 Adobe Campaign Standard，則可使用 Adobe Campaign Standard 的[「交易訊息」功能](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=zh-Hant)來傳送電子郵件、推播通知和簡訊。

在事件設定索引標籤中，**技術使用者**&#x200B;會設定歷程中預期的事件。會依照 Adobe Experience Data Model (XDM)，對傳入事件的資料進行標準化。事件來自串流獲取 API，適用於驗證和未驗證的事件（例如 Adobe Mobile SDK 事件）。

在資料來源設定索引標籤中，**技術使用者**&#x200B;會設定：

* 歷程設計程式中 Adobe Experience Platform 公開的不同欄位，以用於建立條件和個人化目的。
* 您在歷程設計程式中善用的其他自訂資料來源。自訂資料來源是指透過 API 在 [!DNL Journey Orchestration] 和協力廠商系統或服務之間的連線。您可以連線協力廠商系統，例如忠誠度系統。例如，協力廠商服務可以是氣象 API。

有了歷程設計程式，**業務使用者**&#x200B;就可輕鬆地拖放入口事件、新增條件並指定要執行的動作。

之後，您就能根據下列項目建立條件：

* 時間
* 來自事件有效負載的資料
* 來自資料來源的資訊：即時客戶輪廓資料來源或自訂資料來源

您可以使用分割條件，將歷程中的人們引導至不同的方向。

之後，您可以使用動作活動，透過協力廠商系統傳送訊息。如果您擁有 Adobe Campaign Standard，請傳送即時個人化簡訊、推播通知或電子郵件。

由於 [!DNL Journey Orchestration] 需要執行多個步驟，您可以建立進階情境。例如，在第一個事件和動作之後，您可以拖曳其他事件。之後，您可以新增第二個動作、放置等待活動以等待一段時間、新增分割條件，以便將人們推送至兩個不同的路徑，然後再傳送不同的訊息。

>[!NOTE]
>
>本文件將經常更新，以反應產品近期異動。不過，有些螢幕擷取畫面可能會與產品的介面稍有不同。
