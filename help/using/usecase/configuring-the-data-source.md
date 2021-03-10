---
product: adobe campaign
solution: Journey Orchestration
title: 設定資料來源
description: 瞭解如何針對歷程中的簡單使用案例設定資料來源
feature: 旅程
role: 業務從業人員
level: 中級
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 6%

---


# 設定資料來源{#concept_ax3_bcy_w2b}

在我們的使用案例中，我們想要將個人化資料用於我們的訊息。 我們還需要檢查一下這個人是女人。 此資訊會儲存在即時客戶個人檔案資料庫中。 **技術使用者**&#x200B;需要檢查這些欄位是否已在內建的Adobe Experience Platform資料來源中定義。

有關資料源配置的其他資訊，請參閱[本頁](../datasource/about-data-sources.md)。

1. 在頂部菜單中，按一下&#x200B;**[!UICONTROL Data Sources]**&#x200B;頁籤並選擇內置的Adobe Experience Platform資料源。

   ![](../assets/journey23.png)

1. 在欄位群組中，檢查下列欄位是否已選取：

   * _person > name > firstName_
   * _person > name > lastName_
   * _人員>性別_
   * _個人電子郵件>地址_

1. 按一下 **[!UICONTROL Save]**。

資料來源現在已設定好，可供您在歷程中使用。
