---
product: adobe campaign
title: 選取命名空間
description: 了解如何選取命名空間
feature: Journeys
role: User
level: Intermediate
exl-id: 976c6353-797e-40cc-bb90-5d82381bb903
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 10%

---

# 選取命名空間 {#concept_ckb_3qt_52b}

命名空間可讓您定義用於識別與事件相關聯之人員的索引鍵類型。 其設定為選用。 如果您想在歷程中擷取來自 [即時客戶個人檔案](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant). 如果您只使用來自協力廠商系統的資料（透過自訂資料來源），則不需要命名空間定義。

您可以使用其中一個預先定義的命名空間，或使用身分命名空間服務建立新的一個。 請參閱 [頁面](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=zh-Hant).

如果您選取的架構具有主要身分，則 **[!UICONTROL Key]** 和 **[!UICONTROL Namespace]** 欄位已預填。 如果沒有定義標識，則我們選擇 _identityMap > id_ 作為主要金鑰。 然後，您必須選取命名空間，系統就會預先填入索引鍵(位於 **[!UICONTROL Namespace]** 欄位)使用 _identityMap > id_.

選取欄位時，會標籤主要身分欄位。

![](../assets/primary-identity.png)


從下拉式清單中選取命名空間。

![](../assets/journey17.png)

每個歷程僅允許一個命名空間。 如果您在相同歷程中使用數個事件，則這些事件需要使用相同的命名空間。 請參閱[此頁面](../building-journeys/journey.md)。
