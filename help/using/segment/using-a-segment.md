---
product: adobe campaign
solution: Journey Orchestration
title: 使用區段
description: 瞭解如何使用區段
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: a99ad6a589bcd1f3083eabbcac35dd5c0497093d
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 2%

---


# 在條件中使用區段 {#using-a-segment}

本節說明如何在歷程條件中使用區段。 若要瞭解如何在歷程中使用&#x200B;**[!UICONTROL Segment qualification]**&#x200B;事件，請參閱此[章節](../building-journeys/segment-qualification-events.md)。

若要在歷程條件中使用區段，請遵循下列步驟：

1. 開啟歷程，放下&#x200B;**[!UICONTROL Condition]**&#x200B;活動，然後選擇&#x200B;**資料來源條件**。
   ![](../assets/journey47.png)

1. 按一下&#x200B;**[!UICONTROL Add a path]**&#x200B;以查看每個需要的額外路徑。 對於每個路徑，按一下&#x200B;**[!UICONTROL Expression]**&#x200B;欄位。

   ![](../assets/segment3.png)

1. 在左側展開&#x200B;**[!UICONTROL Segments]**&#x200B;節點。 拖放您要用於條件的區段。 依預設，區段上的條件為true。

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >只有具有&#x200B;**Remailed**&#x200B;和&#x200B;**Existing**&#x200B;區段參與狀態的個人才會被視為區段的成員。 如需如何評估區段的詳細資訊，請參閱[區段服務檔案](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results)。

有關歷程條件以及如何使用簡單運算式編輯器的詳細資訊，請參閱[Condition活動](../building-journeys/condition-activity.md#about_condition)。