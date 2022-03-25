---
product: adobe campaign
title: 運用疲勞分數
description: 瞭解如何在旅途中利用疲勞分數
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 10%

---


# 善用歷程 AI {#concept_dsh_1ry_wfb}

此使用案例將向您展示如何利用疲勞評分來避免在您的旅途中過度招攬客戶。

>[!NOTE]
>
>預測疲勞分數功能僅適用於使用 [Adobe Experience Platform資料連接器](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html)。

## 設定事件 {#section_ptb_ws1_ffb}

按照中介紹的步驟操作 [此頁](../event/about-events.md)。

## 設定資料來源 {#section_o3n_4yy_wfb}

執行以下步驟以選擇內置資料源中的已多次聯繫的分數欄位：

1. 在菜單窗格中，選擇 **[!UICONTROL Admin]**。 在 **[!UICONTROL Data sources]** ，按一下 **[!UICONTROL Manage]**。
1. 選擇內置的Adobe Experience Platform資料源。

   ![](../assets/journey23.png)

1. 檢查是否選擇了用例所需的欄位。
1. 按一下 **[!UICONTROL Add a New Field Group]**，選擇 **[!UICONTROL Profiles]** 模型並添加 **[!UICONTROL fatigueLevel]** 和 **[!UICONTROL fatigueScore]** 欄位（下） _journeyAI > emailScore >疲勞_)。

   ![](../assets/journeyuc3_1.png)

1. 按一下「**[!UICONTROL Save]**」。

## 建立歷程 {#section_uzm_pyy_wfb}

要建立、驗證和發佈行程，請遵循中介紹的步驟 [此頁](../building-journeys/journey.md)。

在使用案例中，我們利用 **[!UICONTROL fatigueLevel]** 的子菜單。 您還可以使用 **[!UICONTROL fatigueScore]** 的子菜單。

執行以下步驟以利用旅途中的疲勞級別：

1. 在行程中添加事件和條件。

   ![](../assets/journeyuc2_14.png)

1. 選擇 **[!UICONTROL Data Source Condition]** 類型，然後按一下 **[!UICONTROL Expression]** 欄位。

   ![](../assets/journeyuc3_2.png)

1. 使用簡單表達式編輯器，查找 **[!UICONTROL fatigueLevel]** 欄位(D)_ExperiencePlatformDataSource > JourneyAIScores >配置檔案> journeyAI >電子郵件分數>已疲勞_)，將其向右放置並建立以下條件：&quot;fatigueLevel等於&quot;Low&quot;。 按一下「**[!UICONTROL Ok]**」。

   ![](../assets/journeyuc3_3.png)

   高級表達式為：

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. 在該條件下，為中等疲勞水準和高疲勞水準建立兩個其它路徑。

   ![](../assets/journeyuc3_4.png)

1. 現在，您可以為每個疲勞級別添加不同的動作。

   ![](../assets/journeyuc3_5.png)
