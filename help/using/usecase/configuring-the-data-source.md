---
product: adobe campaign
solution: Journey Orchestration
title: 設定資料來源
description: 瞭解如何針對歷程中的簡單使用案例設定資料來源
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 6%

---


# 設定資料來源{#concept_ax3_bcy_w2b}

在我們的使用案例中，我們想要將個人化資料用於我們的訊息。 我們還需要檢查一下這個人是女人。 此資訊會儲存在即時客戶個人檔案資料庫中。 技 **術使用者** ，必須檢查這些欄位是否已在內建的Adobe Experience Platform資料來源中定義。

有關資料源配置的其他資訊，請參 [閱此頁](../datasource/about-data-sources.md)。

1. 在頂端功能表中，按一 **[!UICONTROL Data Sources]** 下標籤並選取內建的Adobe Experience Platform資料來源。

   ![](../assets/journey23.png)

1. 在欄位群組中，檢查下列欄位是否已選取：

   * _person > name > firstName_
   * _person > name > lastName_
   * _人員>性別_
   * _個人電子郵件>地址_

1. 按一下 **[!UICONTROL Save]**。

資料來源現在已設定好，可供您在歷程中使用。
