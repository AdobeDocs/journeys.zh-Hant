---
product: adobe campaign
solution: Journey Orchestration
title: 'Adobe Experience Platform 資料來源 '
description: '瞭解如何設定Adobe Experience Platform資料來源 '
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 11%

---


# Adobe Experience Platform 資料來源 {#concept_zrb_nqt_52b}

Adobe Experience Platform資料源定義與即時客戶概要服務的連接。 此資料來源已內建並預先設定。 無法刪除。 此資料來源的設計目的是從即時客戶個人檔案服務中擷取和使用資料（例如，檢查進入歷程的人是否為女性）。 它可讓您使用描述檔資料和體驗事件資料。 有關即時客戶概要服務的詳細資訊，請參閱此[頁](https://docs.adobe.com/content/help/zh-Hant/experience-platform/profile/home.html)。

>[!NOTE]
>
>您可以擷取不到一年前建立的1000個最新體驗事件。

若要允許連線至即時客戶個人檔案服務，我們必須使用金鑰來識別人員，並使用將金鑰加上文字的命名空間。 因此，若您的歷程是從包含索引鍵和命名空間的事件開始，則只能使用此資料來源。 請參閱[本頁](../building-journeys/journey.md)。

您可以編輯名為「ProfileFieldGroup」的預先設定欄位群組，新增欄位群組，並移除未用於任何草稿或即時歷程的欄位群組。 請參閱[本頁](../datasource/field-groups.md)。

以下是將欄位群組新增至內建資料來源的主要步驟。

1. 從資料來源清單中，選取內建的Adobe Experience Platform資料來源。

   這會開啟畫面右側的資料來源設定窗格。

   ![](../assets/journey23.png)

1. 按一下&#x200B;**[!UICONTROL Add a New Field Group]**&#x200B;可定義要檢索的新一系列欄位。 請參閱[本頁](../datasource/field-groups.md)。

   ![](../assets/journey24.png)

1. 從&#x200B;**[!UICONTROL Schema]**&#x200B;下拉式清單中選擇架構。 此欄位會列出Adobe Experience Platform的「描述檔」和「體驗事件」結構描述。 在[!DNL Journey Orchestration]中不執行模式建立。 它在Adobe Experience Platform演出。
1. 選取您要使用的欄位。
1. 定義快取持續時間。
1. 按一下&#x200B;**[!UICONTROL Save]**。

當您將游標置於欄位群組的名稱上時，您會在右側看到兩個圖示。 這些欄位可讓您刪除和複製欄位群組。 請注意，**[!UICONTROL Delete]**&#x200B;圖示只有在欄位群組未用於任何即時或草稿歷程時才可用（資訊顯示在&#x200B;**[!UICONTROL Used in]**&#x200B;欄位中）。
