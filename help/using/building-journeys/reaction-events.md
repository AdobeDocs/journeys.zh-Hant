---
product: adobe campaign
title: 反應事件
description: 瞭解反應事件
feature: Journeys
role: User
level: Intermediate
exl-id: 2f2a2905-1521-48d9-b593-9b31238282a5
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 2%

---

# 反應事件 {#section_dhx_gss_dgb}

在元件面板中提供的不同事件活動中，您將發現 **[!UICONTROL Reactions]** 的子菜單。 此活動允許您對與通過電子郵件、簡訊發送的消息相關的跟蹤資料做出反應，或在同一行程內推送活動。 此資訊來自Adobe Campaign Standard的事務性消息傳遞。 我們在與Adobe Experience Platform分享資訊時即時捕獲這些資訊。 對於推送通知，您可以對按一下的、發送的或失敗的消息做出響應。 對於SMS消息，您可以對已發送或失敗的消息做出響應。 對於電子郵件，您可以對按一下的、發送的、開啟的或失敗的郵件做出反應。

您還可以使用此機制在消息沒有反應時執行操作。 為此，請建立與反應活動平行的第二條路徑，並添加等待活動。 如果在等待活動中定義的期間內沒有反應，則將選擇第二條路徑。 您可以選擇發送後續消息。

請注意，只有在前面有電子郵件、推送或SMS活動時，您才能在畫布中使用反應活動。

請參閱 [關於操作活動](../building-journeys/about-action-activities.md)。

![](../assets/journey45.png)

以下是配置反應事件的不同步驟：

1. 添加 **[!UICONTROL Label]** 反應。 此步驟為選填。
1. 從下拉清單中，選擇要對其做出反應的操作活動。 您可以選擇在路徑的前幾個步驟中定位的任何活動。
1. 根據您選擇的操作（電子郵件、SMS或推送通知），選擇您要回應的內容。
1. 您可以定義事件超時（40秒到30天之間）和超時路徑。 這將為未在定義的持續時間內做出反應的個人建立第二條路徑。 測試使用反應事件的行程時，test模式 **[!UICONTROL Wait time]** 預設值和最小值為40秒。 請參閱[本節](../building-journeys/testing-the-journey.md)。

>[!NOTE]
>
>Reactions事件與Adobe Campaign Standard協作，無論它部署在AWS或Azure伺服器上。
>
>反應事件無法跟蹤在不同行程中發生的電子郵件、簡訊或推送操作。
>
>反應事件跟蹤「跟蹤」類型連結的點擊量(請參閱 [頁](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/links.html#about-tracked-urls))。 未考慮取消訂閱和鏡像頁面連結。

>[!IMPORTANT]
>
>電子郵件客戶端（如Gmail）允許阻止影像。 使用電子郵件中包含的0像素影像跟蹤開啟的電子郵件。 如果影像被阻止，則開啟的電子郵件將不被考慮在內。
