---
product: adobe campaign
title: 歷程步驟分享概覽
description: 歷程步驟分享概覽
feature: Journeys
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: 034473b318eddf93e4ed27d9cbe9e18dab1d96cb
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 5%

---

# 歷程步驟分享概覽{#sharing-overview}

[!DNL Journey Orchestration] 自動將行程效能資料發送到Adobe Experience Platform，以便與其他資料組合以便進行分析。

>[!NOTE]
>
>預設情況下，在所有實例上都會激活此功能，用於行程步驟事件。 對於行程簡檔步驟事件，應要求激活。 您不能修改或更新在為步驟事件設定期間建立的架構和資料集。 預設情況下，這些架構和資料集處於只讀模式。

例如，您已設定了發送多個電子郵件的行程。 此功能允許您將 [!DNL Journey Orchestration] 與下游事件資料的資料，如發生了多少次轉換、網站上發生了多少項參與，或在儲存中發生了多少事務。 行程資訊可以與Adobe Experience Platform上的資料組合，或者從其他數字屬性或從離線屬性中組合，以提供更全面的效能視圖。

[!DNL Journey Orchestration] 自動為每個人在旅途中採取的每一步建立必要的模式和資料流到Adobe Experience Platform資料集。 步驟事件對應於在行程中從一個節點移動到另一個節點的個人。 例如，在具有事件、條件和動作的旅程中，三步事件被發送到Adobe Experience Platform。

傳遞的XDM欄位清單是全面的。 有些包含系統生成的代碼，有些則具有可讀的友好名稱。 示例包括行程活動的標籤或步驟狀態：操作超時或錯誤結束的次數。

>[!CAUTION]
>
>無法為即時配置檔案服務開啟資料集。 請確保 **[!UICONTROL Profile]** 切換被關閉。

旅程在資料發生時以流式傳輸方式發送資料。 您可以使用查詢服務查詢此資料。 您可以連接到Customer Journey Analytics或其他BI工具，以查看與這些步驟相關的資料。

將建立以下架構：

* 行程步驟配置檔案事件架構 [!DNL Journey Orchestration]  — 體驗事件，用於在行程中執行的步驟以及用於映射到單個行程參與者的身份映射。
* 行程步驟事件架構 [!DNL Journey Orchestration]  — 與行程元資料相關聯的行程步驟事件。
* 帶行程欄位的行程架構 [!DNL Journey Orchestration]  — 描述旅程的旅程元資料。

![](../assets/sharing1.png)

![](../assets/sharing2.png)

傳遞了以下資料集：

* 行程步驟配置檔案事件架構 [!DNL Journey Orchestration]
* 旅程事件
* 歷程

![](../assets/sharing3.png)

傳遞給Adobe Experience Platform的XDM欄位清單在下面詳細介紹：

* [步驟事件欄位清單](../building-journeys/sharing-field-list.md)
* [舊版步驟事件欄位](../building-journeys/sharing-legacy-fields.md)

有關向Adobe Experience Platform報告的步驟事件的詳細資訊，請觀看此 [教程視頻](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html)。

## 與客戶行程分析整合{#integration-cja}

Journey Orchestration步驟事件可以連結到中的其他資料集 [AdobeCustomer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hant)。 以下是一般工作流：

* Customer Journey Analytics接收「Journey Step Event」資料集。
* 的 **配置檔案ID** 關聯的「Journey Orchestration的行程步驟事件模式」中的欄位定義為「標識」欄位。 在Customer Journey Analytics中，然後可以將此資料集連結到與基於人員的標識符具有相同值的任何其他資料集。
* 如果要在Customer Journey Analytics中使用此資料集，請參閱此 [文檔](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/cross-channel.html)。
