---
title: 'Adobe Experience Platform 資料來源 '
description: '瞭解如何設定Adobe Experience Platform資料來源 '
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: e353d593ab2710f50a88a3715378c86c2e37b4f6
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 11%

---


# Adobe Experience Platform 資料來源 {#concept_zrb_nqt_52b}

Adobe Experience Platform資料來源定義即時客戶個人檔案服務的連線。 此資料來源已內建並預先設定。 無法刪除。 此資料來源的設計目的是從即時客戶個人檔案服務中擷取和使用資料（例如，檢查進入歷程的人是否為女性）。 它可讓您使用描述檔資料和體驗事件資料。 如需即時客戶個人檔案服務的詳細資訊，請參閱本 [頁](https://docs.adobe.com/content/help/zh-Hant/experience-platform/profile/home.html)。

>[!NOTE]
>
>您可以擷取不到一年前建立的1000個最新體驗事件。

若要允許連線至即時客戶個人檔案服務，我們必須使用金鑰來識別人員，並使用將金鑰加上文字的命名空間。 因此，若您的歷程是從包含索引鍵和命名空間的事件開始，則只能使用此資料來源。 請參閱[本頁](../building-journeys/journey.md)。

您可以編輯名為「ProfileFieldGroup」的預先設定欄位群組，新增欄位群組，並移除未用於任何草稿或即時歷程的欄位群組。 請參閱[本頁](../datasource/field-groups.md)。

以下是將欄位群組新增至內建資料來源的主要步驟。

1. 從資料來源清單中，選取內建的Adobe Experience Platform資料來源。

   這會開啟畫面右側的資料來源設定窗格。

   ![](../assets/journey23.png)

1. 按一 **[!UICONTROL Add a New Field Group]** 下以定義要擷取的新欄位系列。 請參閱[本頁](../datasource/field-groups.md)。

   ![](../assets/journey24.png)

1. 從下拉式清單 **[!UICONTROL Schema]** 中選取結構。 此欄位會列出Adobe Experience Platform中的「設定檔」和「體驗事件」結構描述。 在中不執行模式建立 [!DNL Journey Orchestration]。 它是在Adobe Experience Platform中執行。
1. 選取您要使用的欄位。
1. 定義快取持續時間。
1. 按一下 **[!UICONTROL Save]**。

當您將游標置於欄位群組的名稱上時，您會在右側看到兩個圖示。 這些欄位可讓您刪除和複製欄位群組。 請注意， **[!UICONTROL Delete]** 只有在欄位群組未用於任何即時或草稿歷程時（欄位中顯示的資訊），此圖示才 **[!UICONTROL Used in]** 可用。
