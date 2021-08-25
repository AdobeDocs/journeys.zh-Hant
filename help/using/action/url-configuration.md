---
product: adobe campaign
title: URL 組態
description: 了解URL設定
feature: Journeys
role: User
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: e71d641888caa9385d078d9c85e073b5f1ed743f
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 5%

---

# URL 組態 {#concept_gbg_1f1_2gb}

設定自訂動作時，您需要定義下列&#x200B;**[!UICONTROL URL Configuration]**&#x200B;參數：

![](../assets/journeyurlconfiguration.png)

1. 在&#x200B;**[!UICONTROL URL]**&#x200B;欄位中，指定外部服務的URL:

   * 如果URL為靜態，請在此欄位中輸入URL。

   * 如果URL包含動態路徑，則僅輸入URL的靜態部分，即配置、主機、埠，以及路徑的靜態部分（可選）。

      範例：`https://xxx.yyy.com:8080/somethingstatic/`

      將自訂動作新增至歷程時，您會指定URL的動態路徑。 [了解更多](../building-journeys/using-custom-actions.md)。
   >[!NOTE]
   >
   >基於安全考量，強烈建議您為URL使用HTTPS配置。 不允許使用非公用的Adobe位址和IP位址。

1. 選擇呼叫&#x200B;**[!UICONTROL Method]**:可以是&#x200B;**[!UICONTROL POST]**&#x200B;或&#x200B;**[!UICONTROL PUT]**。
1. 在&#x200B;**[!UICONTROL Headers]**&#x200B;區段中，定義要傳送至外部服務的要求訊息的HTTP標題：
   1. 要添加標題欄位，請按一下&#x200B;**[!UICONTROL Add a header field]**。
   1. 輸入標題欄位的鍵。
   1. 要設定鍵值對的動態值，請選擇&#x200B;**[!UICONTROL Variable]**。 否則，請選擇&#x200B;**[!UICONTROL Constant]**。

      例如，對於時間戳記，您可以設定動態值。

   1. 如果已選擇&#x200B;**[!UICONTROL Constant]**，則輸入常數值。

      如果您已選取&#x200B;**[!UICONTROL Variable]**，則會在將自訂動作新增至歷程時指定此變數。 [了解更多](../building-journeys/using-custom-actions.md)。

      ![](../assets/journeyurlconfiguration2.png)

   1. 若要刪除標題欄位，請指向標題欄位，然後按一下&#x200B;**[!UICONTROL Delete]**&#x200B;圖示。
   預設會設定&#x200B;**[!UICONTROL Content-Type]**&#x200B;和&#x200B;**[!UICONTROL Charset]**&#x200B;標題欄位。 您無法修改或刪除這些欄位。

   將自訂動作新增至歷程後，如果歷程處於草稿狀態，您仍可新增標題欄位。 如果您不希望歷程受到設定變更的影響，請複製自訂動作，並將標題欄位新增至新的自訂動作。

   >[!NOTE]
   >
   >標題會根據欄位剖析規則進行驗證。 [了解更多](https://tools.ietf.org/html/rfc7230#section-3.2.4)。
