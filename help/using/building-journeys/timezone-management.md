---
product: adobe campaign
title: 時區管理
description: 瞭解時區管理
feature: Journeys
role: User
level: Intermediate
exl-id: c0e67849-caa0-4045-94ed-38e483054e1d
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 2%

---

# 時區管理 {#timezone_management}

可在 [屬性](../building-journeys/changing-properties.md) 你的旅程。

要訪問「屬性」，請按一下螢幕右上角的鉛筆表徵圖。

此時區將用於包含時間元素的行程的每個活動，如：

* [時間條件](../building-journeys/condition-activity.md#time_condition)
* [日期條件](../building-journeys/condition-activity.md#date_condition)
* [自定義等待](../building-journeys/wait-activity.md#custom)
* [固定日期等待](../building-journeys/wait-activity.md#fixed_date)

您可以選擇一個時區，或選擇使用用戶配置檔案中定義的時區。

>[!NOTE]
>
>配置檔案時區與 **時區** 欄位 **首選項詳細資訊** 欄位組。

## 定義固定時區 {#fixed-timezone}

時區也可以固定。 清除預定義的時區，然後從下拉清單中選擇一個時區。 如果使用固定的時區，則所有進入行程的個人將使用相同的時區。

為此，請在 **[!UICONTROL Properties]**，選擇時區。

![](../assets/journey72.png)

## 使用配置檔案定義行程時區 {#timezone-from-profiles}

如果旅程的入門事件具有命名空間，即旅程可以到達Adobe Experience Platform的即時客戶概要檔案服務，則時區是預先定義的，該時區在旅程中流動的個人概要檔案中指定。

如果在Adobe Experience Platform配置檔案中定義了時區，則可以在行程中檢索該時區。

如果個人的配置檔案不包含時區，則檢索到的時區將是時區欄位中定義的時區。

為此，請在 **[!UICONTROL Properties]**&#x200B;選中 **[!UICONTROL Use Profile timezone in timers and conditions]**。

![](../assets/journey73.png)

## 在表達式中使用時區 {#timezone-in-expressions}

行程的起始日期和終止日期不能連結到特定時區。 它們會自動與實例的時區關聯。
