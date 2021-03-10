---
product: adobe campaign
solution: Journey Orchestration
title: 定義訊息參數
description: 瞭解如何定義訊息參數
feature: 旅程
role: 業務從業人員
level: 中級
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 3%

---


# 定義訊息參數 {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

在&#x200B;**[!UICONTROL Message parameters]**&#x200B;區段中，貼上JSON裝載的範例以傳送至外部服務。

![](../assets/customactionpayloadmessage.png)

您可以定義參數類型(例如：字串、整數等)。

您也可以選擇指定參數是常數還是變數：

* 常數表示參數的值由技術人員在動作配置窗格中定義。 各個旅程的值一律相同。 在歷程中使用自訂動作時，不會有任何變化，行銷人員也不會看到。 例如，可能是協力廠商系統所預期的ID。 在這種情況下，切換常數／變數右側的欄位是傳遞的值。
* 變數表示參數的值會有所不同。 在歷程中使用此自訂動作的行銷人員可自由傳遞他想要的值，或指定擷取此參數值的位置(例如從事件、從Adobe Experience Platform等)。 在這種情況下，切換常數／變數右側的欄位是行銷人員在命名此參數的歷程中所看到的標籤。

![](../assets/customactionpayloadmessage2.png)
