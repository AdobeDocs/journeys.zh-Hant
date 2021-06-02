---
product: adobe campaign
title: 時區管理
description: 了解時區管理
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: c0e67849-caa0-4045-94ed-38e483054e1d
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 2%

---

# 時區管理 {#timezone_management}

您可以在歷程的[properties](../building-journeys/changing-properties.md)中定義時區。

若要存取「屬性」，請按一下畫面右上方的鉛筆圖示。

此時區將用於歷程中包含時間元素的每個活動，例如：

* [時間條件](../building-journeys/condition-activity.md#time_condition)
* [日期條件](../building-journeys/condition-activity.md#date_condition)
* [自訂等待](../building-journeys/wait-activity.md#custom)
* [固定日期等待](../building-journeys/wait-activity.md#fixed_date)

您可以選取時區或選擇使用使用者設定檔中定義的時區。

## 定義固定時區{#fixed-timezone}

時區也可以固定。 清除預先定義的時區，然後從下拉式清單中選取時區。 如果您使用固定時區，則所有進入歷程的個人都會使用相同時區。

要執行此操作，請在&#x200B;**[!UICONTROL Properties]**&#x200B;中選取時區。

![](../assets/journey72.png)

## 使用設定檔來定義歷程時區{#timezone-from-profiles}

如果歷程的登入事件具有命名空間，表示歷程可存取Adobe Experience Platform的即時客戶個人檔案服務，則會以在歷程中流動之個人的個人檔案中指定的時區來預先定義時區。

如果在Adobe Experience Platform設定檔中定義時區，則可在歷程中擷取。

如果個人的設定檔不包含時區，則擷取的時區將是時區欄位中定義的時區。

要執行此操作，請在&#x200B;**[!UICONTROL Properties]**&#x200B;中檢查&#x200B;**[!UICONTROL Use Profile timezone in timers and conditions]**。

![](../assets/journey73.png)

## 在運算式{#timezone-in-expressions}中使用時區

歷程的開始和結束日期無法連結至特定時區。 它們會自動與執行個體的時區相關聯。
