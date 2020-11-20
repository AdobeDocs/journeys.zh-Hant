---
product: adobe campaign
solution: Journey Orchestration
title: URL 組態
description: 瞭解URL設定
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 9%

---


# URL 組態 {#concept_gbg_1f1_2gb}

設定自訂動作時，您需要定義下列參 **[!UICONTROL URL Configuration]** 數：

![](../assets/journeyurlconfiguration.png)

1. Add the **[!UICONTROL URL]** of the external service.

   >[!NOTE]
   >
   >基於安全考量，我們強烈建議您使用 HTTPS。我們不允許使用非公開的Adobe位址和IP位址。

1. 選擇呼叫 **[!UICONTROL Method]**:它可以是 **[!UICONTROL POST]** 或 **[!UICONTROL PUT]**。
1. 在節 **[!UICONTROL Headers]** 中，單 **[!UICONTROL Add a header field]** 擊以定義新鍵／值對。 它們對應於對外部服務所提出請求的HTTP標頭。 要刪除鍵／值對，請將游標置於欄位上， **[!UICONTROL Headers]** 然後按一下圖 **[!UICONTROL Delete]** 標。

   **[!UICONTROL Content-Type]** 和 **[!UICONTROL Charset]** 預設設定，且無法刪除或覆寫。

   >[!NOTE]
   >
   >標題會根據下列解析規則 [進行驗證](https://tools.ietf.org/html/rfc7230#section-3.2.4)。
