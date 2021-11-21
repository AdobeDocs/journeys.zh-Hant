---
product: adobe campaign
title: 定義動作參數
description: 了解如何定義動作參數
feature: Journeys
role: User
level: Intermediate
exl-id: ea9cdb1d-dde6-4080-8f35-7f8cd3cf3644
source-git-commit: 7ce4ddec60f62662d67351b8ca70d7763e76b977
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 4%

---

# 定義動作參數 {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

在 **[!UICONTROL Action parameters]** 區段中，貼上要傳送至外部服務的JSON裝載範例。

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>裝載中的欄位名稱不能包含「。」 字元. 開頭不能為「$」字元。

您將能定義參數類型(例如：字串、整數等)。

您也可以選擇指定參數為常數或變數：

* 常數表示參數的值是由技術人員在動作設定窗格中定義。 歷程中的值一律相同。 此值不會有所不同，且行銷人員在歷程中使用自訂動作時不會看到。 例如可能是協力廠商系統預期的ID。 在此情況下，切換常數/變數右側的欄位即為傳遞的值。
* 變數表示參數的值會有所不同。 在歷程中使用此自訂動作的行銷人員將可自由傳遞所需值，或指定要擷取此參數值的位置(例如從事件、從Adobe Experience Platform等)。 在此情況下，切換常數/變數右側的欄位，即為行銷人員在歷程中看到的用以命名此參數的標籤。

![](../assets/customactionpayloadmessage2.png)
