---
product: adobe campaign
title: 'Adobe Experience Platform 資料來源 '
description: '瞭解如何配置Adobe Experience Platform資料源 '
feature: Journeys
role: User
level: Intermediate
exl-id: 847fa819-2b92-49e5-8a5e-4f3f0acd5e35
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 11%

---

# Adobe Experience Platform 資料來源 {#concept_zrb_nqt_52b}

Adobe Experience Platform資料源定義與即時客戶配置檔案服務的連接。 此資料源是內置的並預先配置的。 無法刪除。 此資料源旨在從即時客戶配置檔案服務中檢索和使用資料（例如，檢查輸入行程的人員是否為女性）。 它允許您使用配置檔案資料和體驗事件資料。 有關即時客戶配置檔案服務的詳細資訊，請參閱此 [頁](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant)。

>[!NOTE]
>
>您可以檢索不到一年前建立的1000個最新體驗事件。

要允許與即時客戶配置檔案服務的連接，我們必須使用一個鍵來標識一個人，以及一個將該鍵置於上下文的命名空間。 因此，僅當您的行程以包含密鑰和命名空間的事件開頭時，才能使用此資料源。 請參閱[此頁面](../building-journeys/journey.md)。

您可以編輯名為「ProfileFieldGroup」的預配置欄位組，添加新欄位組，並刪除未在任何草稿或即時行程中使用的欄位組。 請參閱[此頁面](../datasource/field-groups.md)。

以下是向內置資料源添加欄位組的主要步驟。

1. 從資料源清單中，選擇內置的Adobe Experience Platform資料源。

   這會開啟畫面右側的資料來源設定窗格。

   ![](../assets/journey23.png)

1. 按一下 **[!UICONTROL Add a New Field Group]** 定義要檢索的新系列欄位。 請參閱[此頁面](../datasource/field-groups.md)。

   ![](../assets/journey24.png)

1. 從 **[!UICONTROL Schema]** 下拉。 此欄位列出了Adobe Experience Platform中可用的配置檔案和體驗事件架構。 未在中執行架構建立 [!DNL Journey Orchestration]。 在Adobe Experience Platform演。
1. 選擇要使用的欄位。
1. 按一下 **[!UICONTROL Save]**。

將游標置於欄位組的名稱上時，將在右側看到兩個表徵圖。 它們允許您刪除和複製欄位組。 請注意 **[!UICONTROL Delete]** 表徵圖僅在欄位組未用於任何即時或草稿行程(顯示在 **[!UICONTROL Used in]** )。
