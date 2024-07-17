---
product: adobe campaign
title: 運用疲勞分數
description: 瞭解如何在歷程中運用疲勞分數
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 4%

---


# 善用歷程AI {#concept_dsh_1ry_wfb}

此使用案例會說明如何運用疲勞分數，避免在您的歷程中過度向客戶提供促銷。

>[!NOTE]
>
>預測性疲勞分數功能僅適用於使用[Adobe Experience Platform Data Connector](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html)的客戶。

## 設定事件 {#section_ptb_ws1_ffb}

請依照[此頁面](../event/about-events.md)中說明的步驟操作。

## 設定資料來源 {#section_o3n_4yy_wfb}

執行以下步驟，在內建資料來源中選取疲勞分數欄位：

1. 在功能表窗格中，選取&#x200B;**[!UICONTROL Admin]**。 在&#x200B;**[!UICONTROL Data sources]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Manage]**。
1. 選取內建的Adobe Experience Platform資料來源。

   ![](../assets/journey23.png)

1. 檢查是否選取使用案例所需的欄位。
1. 按一下&#x200B;**[!UICONTROL Add a New Field Group]**，選取&#x200B;**[!UICONTROL Profiles]**&#x200B;模型並新增&#x200B;**[!UICONTROL fatigueLevel]**&#x200B;和&#x200B;**[!UICONTROL fatigueScore]**&#x200B;欄位（_journeyAI > emailScore > fatigue_&#x200B;底下）。

   ![](../assets/journeyuc3_1.png)

1. 按一下「**[!UICONTROL Save]**」。

## 建立歷程 {#section_uzm_pyy_wfb}

若要建立、驗證及發佈歷程，請依照[此頁面](../building-journeys/journey.md)中所述的步驟進行。

在我們的使用案例中，我們運用&#x200B;**[!UICONTROL fatigueLevel]**&#x200B;欄位。 您也可以使用&#x200B;**[!UICONTROL fatigueScore]**&#x200B;欄位。

執行以下步驟來運用歷程中的疲勞層級：

1. 在您的歷程中新增事件和條件。

   ![](../assets/journeyuc2_14.png)

1. 選擇&#x200B;**[!UICONTROL Data Source Condition]**&#x200B;型別，然後按一下&#x200B;**[!UICONTROL Expression]**&#x200B;欄位。

   ![](../assets/journeyuc3_2.png)

1. 使用簡單運算式編輯器，尋找&#x200B;**[!UICONTROL fatigueLevel]**&#x200B;欄位(_ExperiencePlatformDataSource > JourneyAIScores > Profile > journeyAI > emailScore > fatigue_)，將其拖曳至右側並建立下列條件： &quot;fatigueLevel equal is &quot;Low&quot;。 按一下「**[!UICONTROL Ok]**」。

   ![](../assets/journeyuc3_3.png)

   進階運算式為：

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. 在條件中，為中及高疲勞等級建立另外兩個路徑。

   ![](../assets/journeyuc3_4.png)

1. 您現在可以為每個疲勞層級新增不同的動作。

   ![](../assets/journeyuc3_5.png)
