---
product: adobe campaign
title: URL 組態
description: 了解URL設定
feature: Journeys
role: User
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: 2a93bce42ea9f1f21d70c68da3dbc36844dafd1b
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 4%

---

# URL 組態 {#concept_gbg_1f1_2gb}

設定自訂動作時，您需要定義下列項目 **[!UICONTROL URL Configuration]** 參數：

![](../assets/journeyurlconfiguration.png)

1. 在 **[!UICONTROL URL]** 欄位，指定外部服務的URL:

   * 如果URL為靜態，請在此欄位中輸入URL。

   * 如果URL包含動態路徑，則僅輸入URL的靜態部分，即配置、主機、埠，以及路徑的靜態部分（可選）。

      範例: `https://xxx.yyy.com/somethingstatic/`

      將自訂動作新增至歷程時，您會指定URL的動態路徑。 [了解更多](../building-journeys/using-custom-actions.md)。
   >[!NOTE]
   >
   >基於安全考量，強烈建議您為URL使用HTTPS配置。 不允許使用非公用的Adobe位址和IP位址。
   >
   >定義自訂動作時，僅允許預設埠：80（適用於http）和443（適用於https）。

1. 選取呼叫 **[!UICONTROL Method]**:它可以是 **[!UICONTROL POST]** 或 **[!UICONTROL PUT]**.
1. 在 **[!UICONTROL Headers]** 一節，定義要傳送至外部服務的要求訊息的HTTP標題：
   1. 若要新增標題欄位，請按一下 **[!UICONTROL Add a header field]**.
   1. 輸入標題欄位的鍵。
   1. 若要設定機碼值組的動態值，請選取 **[!UICONTROL Variable]**. 否則，請選取 **[!UICONTROL Constant]**.

      例如，對於時間戳記，您可以設定動態值。

   1. 如果您已選取 **[!UICONTROL Constant]**，然後輸入常數值。

      如果您已選取 **[!UICONTROL Variable]**，則會在將自訂動作新增至歷程時指定此變數。 [了解更多](../building-journeys/using-custom-actions.md)。

      ![](../assets/journeyurlconfiguration2.png)

   1. 若要刪除標題欄位，請指向標題欄位，然後按一下 **[!UICONTROL Delete]** 表徵圖。
   此 **[!UICONTROL Content-Type]** 和 **[!UICONTROL Charset]** 預設會設定標題欄位。 您無法修改或刪除這些欄位。

   將自訂動作新增至歷程後，如果歷程處於草稿狀態，您仍可新增標題欄位。 如果您不希望歷程受到設定變更的影響，請複製自訂動作，並將標題欄位新增至新的自訂動作。

   >[!NOTE]
   >
   >標題會根據欄位剖析規則進行驗證。 [了解更多](https://tools.ietf.org/html/rfc7230#section-3.2.4)。
