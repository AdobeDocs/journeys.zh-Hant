---
product: adobe campaign
title: 在條件中使用區段
description: 瞭解如何使用段
feature: Journeys
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
source-git-commit: 9db330405130b14d1d8a8cbed59f612fd1f6767b
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 4%

---

# 在條件中使用區段 {#using-a-segment}

本節說明如何在行程條件中使用段。 瞭解如何使用 **[!UICONTROL Segment qualification]** 在您的旅途中的事件，請參閱 [節](../building-journeys/segment-qualification-events.md)。

要在行程條件中使用段，請執行以下步驟：

1. 開路，放下 **[!UICONTROL Condition]** 活動，然後選擇 **資料源條件**。
   ![](../assets/journey47.png)

1. 按一下 **[!UICONTROL Add a path]** 每條額外路徑。 對於每個路徑，按一下 **[!UICONTROL Expression]** 的子菜單。

   ![](../assets/segment3.png)

1. 在左側， **[!UICONTROL Segments]** 的下界。 拖放要用於條件的段。 預設情況下，段上的條件為true。

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >只有那些 **已實現** 和 **現有** 段參與狀態將被視為段的成員。 有關如何評估段的詳細資訊，請參閱 [分段服務文檔](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results)。

有關行程條件以及如何使用簡單表達式編輯器的詳細資訊，請參閱 [條件活動](../building-journeys/condition-activity.md#about_condition)。
