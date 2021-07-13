---
product: adobe campaign
title: 設定資料來源
description: 了解如何為歷程的簡單使用案例設定資料來源
feature: 歷程
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 7%

---

# 設定資料來源{#concept_ax3_bcy_w2b}

在我們的使用案例中，我們想要將個人化資料用於訊息。 我們還需要檢查這個人是女人。 此資訊會儲存在即時客戶設定檔資料庫中。 **技術使用者**&#x200B;需要檢查這些欄位是否已在內建的Adobe Experience Platform資料來源中定義。

有關資料源配置的其他資訊，請參閱[此頁](../datasource/about-data-sources.md)。

1. 在頂端功能表中，按一下&#x200B;**[!UICONTROL Data Sources]**&#x200B;標籤並選取內建的Adobe Experience Platform資料來源。

   ![](../assets/journey23.png)

1. 在欄位群組中，檢查是否已選取下列欄位：

   * _person > name > firstName_
   * _person > name > lastName_
   * _人員>性別_
   * _個人電子郵件>地址_

1. 按一下「**[!UICONTROL Save]**」。

資料來源現在已設定完畢，且可供您在歷程中使用。
