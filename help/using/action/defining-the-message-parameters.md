---
product: adobe campaign
title: 定義動作參數
description: 瞭解如何定義動作引數
feature: Journeys
role: User
level: Intermediate
exl-id: ea9cdb1d-dde6-4080-8f35-7f8cd3cf3644
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 3%

---

# 定義動作參數 {#concept_wy4_bf1_2gb}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_


![](../assets/messageparameterssection.png)

在&#x200B;**[!UICONTROL Action parameters]**&#x200B;區段中，貼上要傳送至外部服務的JSON裝載範例。

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>承載中的欄位名稱不得包含「。」 字元。 開頭不能為「$」字元。

您將能夠定義引數型別（例如：字串、整數等）。

您也可以選擇指定引數是常數還是變數：

* 常數表示引數的值是由技術角色在動作設定窗格中定義。 值在歷程中一律相同。 這不會改變，且行銷人員在歷程中使用自訂動作時不會看到。 例如，它可能是協力廠商系統期望的ID。 在這種情況下，切換常數/變數右側的欄位是傳遞的值。
* 變數表示引數的值會有所不同。 在歷程中使用此自訂動作的行銷人員可自由傳遞他想要的值，或指定從何處擷取此引數的值(例如從事件、Adobe Experience Platform等)。 在這種情況下，切換常數/變數右側的欄位是行銷人員在歷程中看到的標籤，以便命名此引數。

![](../assets/customactionpayloadmessage2.png)
