---
title: 關於資料來源
description: '瞭解如何設定資料來源 '
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 100%

---


# 關於資料來源{#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="關於資料來源"
>abstract="資料來源設定一律會由技術使用者執行。資料來源設定可讓您定義系統連線，以擷取將用於歷程的其他資訊，例如：條件定義、動作中的參數和個人化資料、自訂等待定義、自訂時區定義。"

資料來源設定可讓您定義系統連線，以擷取將用於歷程的其他資訊，例如：

* [條件定義](../building-journeys/condition-activity.md)
* [動作](../action/action.md)中的參數和個人化資料
* [自定等待定義](../building-journeys/wait-activity.md#custom)
* [時區定義](../building-journeys/timezone-management.md)

如果您的歷程僅運用來自事件裝載的本機資料，則不需要進行此設定。例如，如果您的歷程是由事件組成，之後僅會使用來自事件資料的電子郵件活動，則不需要設定資料來源。

資料來源有兩種類型：

* 預先設定的 Adobe Experience Platform 資料來源可定義「即時客戶個人檔案服務」的連線，這是內建的資料來源。請參閱[](../datasource/adobe-experience-platform-data-source.md)。
* 外部資料來源可讓您定義外部系統的連線，這些是您可以建立的資料來源。請參閱[](../datasource/external-data-sources.md)。

對於每個資料來源，您會使用欄位群組來定義要擷取的資訊。欄位群組是可從資料來源擷取的欄位集。請參閱[](../datasource/field-groups.md)。

如需如何設定 Adobe Experience Platform 資料來源和外部資料來源，以及如何在歷程中尋找和使用資料的詳細資訊，請觀看此[教學課程影片](https://docs.adobe.com/content/help/zh-Hant/journey-orchestration-learn/tutorials/configure-data-sources.html)。

以下是主要的資料來源設定步驟：

>[!NOTE]
>
>資料來源設定一律會由&#x200B;**技術使用者**&#x200B;執行。

1. 在頂端功能表中，按一下 **[!UICONTROL Data Sources]** 索引標籤。

   畫面隨即顯示資料來源。請參閱[](../about/user-interface.md)以瞭解介面的詳細資訊。

   ![](../assets/journey18.png)

1. 然後，您就可以將欄位群組新增至內建的資料來源（請參閱[](../datasource/adobe-experience-platform-data-source.md)），或建立新的外部資料來源（請參閱[](../datasource/external-data-sources.md)）和相關聯的欄位群組（請參閱[](../datasource/field-groups.md)）。

   ![](../assets/journey23.png)

1. 按一下 **[!UICONTROL Save]**。

   資料來源現在已設定完畢，且可供您在歷程中使用。
