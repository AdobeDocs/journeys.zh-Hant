---
title: 定義消息參數
description: 瞭解如何定義訊息參數
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# 定義消息參數 {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

在區 **[!UICONTROL Message parameters]**段中，貼上JSON裝載的範例以傳送至外部服務。


![](../assets/customactionpayloadmessage.png)

您可以定義參數類型是否正確(例如：字串、整數等)。

您也可以選擇指定參數為常數或變數：

* 常數表示參數的值由技術人員在動作配置窗格中定義。 各個歷程的值一律相同。 在歷程中使用自訂動作時，不會有任何變化，行銷人員也不會看到。 例如，可能是協力廠商系統所預期的ID。 在這種情況下，切換常數／變數右側的欄位是傳遞的值。
* 變數表示參數的值會有所不同。 在歷程中使用此自訂動作的行銷人員可自由傳遞所需值，或指定從何處擷取此參數值（例如從事件，從資料平台……）。 在這種情況下，切換常數／變數右側的欄位是行銷人員在命名此參數的歷程中所看到的標籤。
