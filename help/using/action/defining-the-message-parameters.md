---
product: adobe campaign
title: 定義動作參數
description: 瞭解如何定義操作參數
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

在 **[!UICONTROL Action parameters]** 部分，貼上要發送到外部服務的JSON負載示例。

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>負載中的欄位名稱不能包含「。」 字元. 它們不能以「$」字元開頭。

您將能夠定義參數類型(例如：字串、整數等)。

還可以選擇指定參數是常數還是變數：

* 常數表示參數的值在操作配置窗格中由技術角色定義。 不同旅程的價值始終相同。 它不會變化，營銷人員在旅途中使用自定義操作時不會看到它。 例如，可能是第三方系統需要的ID。 在這種情況下，切換常數/變數右側的欄位是傳遞的值。
* 變數表示參數的值將發生變化。 在行程中使用此自定義操作的商家可以自由地傳遞他想要的值或指定檢索此參數值的位置(例如從事件、從Adobe Experience Platform等)。 在這種情況下，切換常數/變數右側的欄位是商家在命名此參數的旅程中將看到的標籤。

![](../assets/customactionpayloadmessage2.png)
