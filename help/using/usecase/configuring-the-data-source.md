---
product: adobe campaign
title: 設定資料來源
description: 瞭解如何為行程簡單使用案例配置資料源
feature: Journeys
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 6%

---

# 設定資料來源{#concept_ax3_bcy_w2b}

在我們的使用案例中，我們希望將個性化資料用於我們的郵件。 我們還需要檢查一下，這個人是女的。 此資訊儲存在Real-time Customer Profile資料庫中。 的 **技術用戶** 需要檢查這些欄位是否在內置的Adobe Experience Platform資料源中定義。

有關資料源配置的其他資訊，請參閱 [此頁](../datasource/about-data-sources.md)。

1. 在菜單窗格中，選擇 **[!UICONTROL Admin]**。 在 **[!UICONTROL Data sources]** ，按一下 **[!UICONTROL Manage]**。
1. 選擇內置的Adobe Experience Platform資料源。

   ![](../assets/journey23.png)

1. 在欄位組中，檢查是否選擇了以下欄位：

   * _person > name > firstName_
   * _person > name > lastName_
   * _人員>性別_
   * _個人電子郵件>地址_

1. 按一下「**[!UICONTROL Save]**」。

資料源現在已配置，並準備在您的旅途中使用。
