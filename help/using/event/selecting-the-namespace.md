---
product: adobe campaign
solution: Journey Orchestration
title: 選取命名空間
description: 瞭解如何選取命名空間
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 12%

---


# 選取命名空間 {#concept_ckb_3qt_52b}

命名空間可讓您定義用來識別與事件關聯之人員的索引鍵類型。 其配置是可選的。 如果您想在歷程中擷取來自[即時客戶資料](https://docs.adobe.com/content/help/zh-Hant/experience-platform/profile/home.html)的其他資訊，則此為必要項。 如果您僅使用來自第三方系統的資料透過自訂資料來源，則不需要命名空間定義。

您可以使用其中一個預先定義的名稱空間，或使用Identity Namespace服務建立新的名稱空間。 請參閱此[頁](https://docs.adobe.com/content/help/zh-Hant/experience-platform/identity/home.html)。

如果選擇具有主標識的方案，則預填充&#x200B;**[!UICONTROL Key]**&#x200B;和&#x200B;**[!UICONTROL Namespace]**&#x200B;欄位。 如果未定義身份，我們將選擇&#x200B;_identityMap > id_&#x200B;作為主鍵。 然後，您必須選擇命名空間，然後使用&#x200B;_identityMap > id_&#x200B;預先填入索引鍵（位於&#x200B;**[!UICONTROL Namespace]**&#x200B;欄位下方）。

選擇欄位時，標籤主標識欄位。

![](../assets/primary-identity.png)


從下拉式清單中選取命名空間。

![](../assets/journey17.png)

每個歷程僅允許一個命名空間。 如果您在同一歷程中使用數個事件，它們需要使用相同的命名空間。 請參閱[本頁](../building-journeys/journey.md)。
