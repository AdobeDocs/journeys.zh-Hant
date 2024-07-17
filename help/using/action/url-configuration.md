---
product: adobe campaign
title: URL 組態
description: 瞭解URL設定
feature: Journeys
role: User
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: 2a93bce42ea9f1f21d70c68da3dbc36844dafd1b
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 3%

---

# URL 組態 {#concept_gbg_1f1_2gb}

設定自訂動作時，您必須定義下列&#x200B;**[!UICONTROL URL Configuration]**&#x200B;個引數：

![](../assets/journeyurlconfiguration.png)

1. 在&#x200B;**[!UICONTROL URL]**&#x200B;欄位中，指定外部服務的URL：

   * 如果URL是靜態的，請在此欄位中輸入URL。

   * 如果URL包含動態路徑，請只輸入URL的靜態部分，也就是配置、主機、連線埠，以及（選擇性）路徑的靜態部分。

     範例：`https://xxx.yyy.com/somethingstatic/`

     將自訂動作新增至歷程時，您將指定URL的動態路徑。 [了解更多](../building-journeys/using-custom-actions.md)。

   >[!NOTE]
   >
   >基於安全考量，我們強烈建議您針對URL使用HTTPS配置。 我們不允許使用非公開的Adobe位址和IP位址。
   >
   >定義自訂動作時只允許預設連線埠：80用於http，443用於https。

1. 選取呼叫&#x200B;**[!UICONTROL Method]**：可以是&#x200B;**[!UICONTROL POST]**&#x200B;或&#x200B;**[!UICONTROL PUT]**。
1. 在&#x200B;**[!UICONTROL Headers]**&#x200B;區段中，定義要傳送至外部服務的要求訊息的HTTP標頭：
   1. 若要新增標頭欄位，請按一下&#x200B;**[!UICONTROL Add a header field]**。
   1. 輸入頁首欄位的鍵。
   1. 若要設定機碼值組的動態值，請選取&#x200B;**[!UICONTROL Variable]**。 否則，請選取&#x200B;**[!UICONTROL Constant]**。

      例如，對於時間戳記，您可以設定動態值。

   1. 如果您已選取&#x200B;**[!UICONTROL Constant]**，請輸入常數值。

      如果您已選取&#x200B;**[!UICONTROL Variable]**，則您將在新增自訂動作至歷程時指定此變數。 [了解更多](../building-journeys/using-custom-actions.md)。

      ![](../assets/journeyurlconfiguration2.png)

   1. 若要刪除標頭欄位，請指向標頭欄位並按一下&#x200B;**[!UICONTROL Delete]**&#x200B;圖示。

   **[!UICONTROL Content-Type]**&#x200B;和&#x200B;**[!UICONTROL Charset]**&#x200B;標頭欄位已預設設定。 您無法修改或刪除這些欄位。

   將自訂動作新增至歷程後，如果歷程處於草稿狀態，您仍可新增標題欄位至歷程。 如果您不希望歷程受設定變更影響，請複製自訂動作，並將標題欄位新增到新的自訂動作。

   >[!NOTE]
   >
   >標頭會根據欄位剖析規則進行驗證。 [了解更多](https://tools.ietf.org/html/rfc7230#section-3.2.4)。
