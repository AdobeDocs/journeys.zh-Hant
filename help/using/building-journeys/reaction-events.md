---
product: adobe campaign
title: 反應事件
description: 了解反應事件
feature: 歷程
role: User
level: Intermediate
exl-id: 2f2a2905-1521-48d9-b593-9b31238282a5
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 2%

---

# 反應事件 {#section_dhx_gss_dgb}

在浮動視窗中可用的不同事件活動中，您會找到內建的&#x200B;**[!UICONTROL Reactions]**&#x200B;事件。 此活動可讓您對與透過電子郵件傳送之訊息、簡訊或在相同歷程中推送活動相關的追蹤資料做出反應。 此資訊來自Adobe Campaign Standard中的交易式訊息。 我們會在與Adobe Experience Platform共用資訊時即時擷取這些資訊。 若是推播通知，您可以對點按、傳送或失敗的訊息做出反應。 對於SMS訊息，您可以對已傳送或失敗的訊息做出反應。 若是電子郵件，您可以對點按、傳送、開啟或失敗的訊息做出反應。

您也可以使用此機制，在訊息沒有反應時執行動作。 要執行此操作，請建立與反應活動平行的第二個路徑，並新增等待活動。 如果在等待活動中定義的期間內沒有反應，則會選擇第二個路徑。 例如，您可以選擇傳送後續訊息。

請注意，您只能在之前有電子郵件、推播或簡訊活動時，使用畫布中的反應活動。

請參閱[關於動作活動](../building-journeys/about-action-activities.md)。

![](../assets/journey45.png)

以下是設定反應事件的不同步驟：

1. 將&#x200B;**[!UICONTROL Label]**&#x200B;新增至反應。 此步驟為選填。
1. 從下拉式清單中，選取您要回應的動作活動。 您可以選取位於路徑前幾個步驟中的任何動作活動。
1. 視您選取的動作（電子郵件、簡訊或推播通知）而定，選擇您要對什麼做出反應。
1. 您可以定義事件逾時（40秒到30天之間）和逾時路徑。 這會為在定義期間內未反應的個人建立第二個路徑。 測試使用反應事件的歷程時，測試模式&#x200B;**[!UICONTROL Wait time]**&#x200B;預設值和最小值為40秒。 請參閱[本節](../building-journeys/testing-the-journey.md)。

>[!NOTE]
>
>反應事件可與Adobe Campaign Standard搭配使用，無論其部署在AWS或Azure伺服器上。
>
>反應事件無法追蹤在不同歷程中發生的電子郵件、簡訊或推播動作。
>
>反應事件會追蹤「tracked」類型之連結上的點按次數（請參閱此[page](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/links.html#about-tracked-urls)）。 未考慮取消訂閱和鏡像頁面連結。

>[!IMPORTANT]
>
>Gmail等電子郵件用戶端允許影像封鎖。 使用電子郵件中包含的0像素影像來追蹤開啟的電子郵件。 如果影像遭到封鎖，系統就不會考慮電子郵件開啟次數。
