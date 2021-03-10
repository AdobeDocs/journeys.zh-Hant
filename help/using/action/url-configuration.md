---
product: adobe campaign
solution: Journey Orchestration
title: URL 組態
description: 瞭解URL設定
feature: 旅程
role: 業務從業人員
level: 中級
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 9%

---


# URL 組態 {#concept_gbg_1f1_2gb}

設定自訂動作時，您需要定義下列&#x200B;**[!UICONTROL URL Configuration]**&#x200B;參數：

![](../assets/journeyurlconfiguration.png)

1. 添加外部服務的&#x200B;**[!UICONTROL URL]**。

   >[!NOTE]
   >
   >基於安全考量，我們強烈建議您使用 HTTPS。我們不允許使用非公開的Adobe地址和IP地址。

1. 選擇呼叫&#x200B;**[!UICONTROL Method]**:可以是&#x200B;**[!UICONTROL POST]**&#x200B;或&#x200B;**[!UICONTROL PUT]**。
1. 在&#x200B;**[!UICONTROL Headers]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Add a header field]**&#x200B;以定義新的鍵／值對。 它們對應於對外部服務所提出請求的HTTP標頭。 要刪除鍵／值對，請將游標置於&#x200B;**[!UICONTROL Headers]**&#x200B;欄位中，然後按一下&#x200B;**[!UICONTROL Delete]**&#x200B;表徵圖。

   **[!UICONTROL Content-Type]** 和 **[!UICONTROL Charset]** 預設設定，不能刪除或覆蓋。

   >[!NOTE]
   >
   >標頭根據以下[解析規則](https://tools.ietf.org/html/rfc7230#section-3.2.4)進行驗證。
