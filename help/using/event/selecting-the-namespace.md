---
product: adobe campaign
title: 選取命名空間
description: 瞭解如何選擇命名空間
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

命名空間允許您定義用於標識與事件關聯的人員的密鑰類型。 其配置是可選的。 如果要在您的行程中檢索來自 [即時客戶概要資訊](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant)。 如果您僅使用來自第三方系統的通過自定義資料源的資料，則不需要命名空間定義。

您可以使用其中一個預定義名稱，或使用Identity Namespace服務建立新名稱。 請參閱此 [頁](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=zh-Hant)。

如果選擇具有主標識的架構，則 **[!UICONTROL Key]** 和 **[!UICONTROL Namespace]** 欄位已預填充。 如果沒有定義標識，我們將選擇 _identityMap > id_ 鍵。 然後，必須選擇一個命名空間，並且該鍵將預填充(位於 **[!UICONTROL Namespace]** 欄位使用 _identityMap > id_。

選擇欄位時，將標籤主標識欄位。

![](../assets/primary-identity.png)


從下拉清單中選擇一個命名空間。

![](../assets/journey17.png)

每個行程只允許一個命名空間。 如果在同一行程中使用多個事件，則它們需要使用相同的命名空間。 請參閱[此頁面](../building-journeys/journey.md)。
