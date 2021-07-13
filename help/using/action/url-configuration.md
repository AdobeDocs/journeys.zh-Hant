---
product: adobe campaign
title: URL 組態
description: 了解URL設定
feature: 歷程
role: User
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 14%

---

# URL 組態 {#concept_gbg_1f1_2gb}

設定自訂動作時，您需要定義下列&#x200B;**[!UICONTROL URL Configuration]**&#x200B;參數：

![](../assets/journeyurlconfiguration.png)

1. 新增外部服務的&#x200B;**[!UICONTROL URL]**。

   >[!NOTE]
   >
   >基於安全考量，我們強烈建議您使用 HTTPS。不允許使用非公用的Adobe位址和IP位址。

1. 選擇呼叫&#x200B;**[!UICONTROL Method]**:可以是&#x200B;**[!UICONTROL POST]**&#x200B;或&#x200B;**[!UICONTROL PUT]**。
1. 在&#x200B;**[!UICONTROL Headers]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Add a header field]**&#x200B;以定義新索引鍵/值組。 它們對應至對外部服務發出之請求的HTTP標題。 若要刪除鍵/值對，請將游標置於&#x200B;**[!UICONTROL Headers]**&#x200B;欄位上，然後按一下&#x200B;**[!UICONTROL Delete]**&#x200B;圖示。

   **[!UICONTROL Content-Type]** 和 **[!UICONTROL Charset]** 預設設定，且無法刪除或覆寫。

   >[!NOTE]
   >
   >標頭根據以下[解析規則](https://tools.ietf.org/html/rfc7230#section-3.2.4)進行驗證。
