---
product: adobe campaign
title: 設定資料來源
description: 瞭解如何設定歷程簡單使用案例的資料來源
feature: Journeys
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 31%
---
# 設定資料來源{#concept_ax3_bcy_w2b}


>[!CAUTION]
>
>**正在尋找 Adobe Journey Optimizer**？ 按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}以取得 Journey Optimizer 文件。
>
>
>_本文件指的是已由 Journey Optimizer 取代的舊版 Journey Orchestration 資料。 如果您對 Journey Orchestration 或 Journey Optimizer 的存取權有任何疑問，請聯絡您的帳戶團隊。_


在我們的使用案例中，我們希望對訊息使用個人化資料。 我們還需要檢查這個人是不是女性。 此資訊儲存在「即時客戶個人檔案」資料庫中。 **技術使用者**&#x200B;需要檢查這些欄位是否已在內建Adobe Experience Platform資料來源中定義。

如需資料來源組態的詳細資訊，請參閱[此頁面](../datasource/about-data-sources.md)。

1. 在功能表窗格中，選取&#x200B;**[!UICONTROL Admin]**。 在&#x200B;**[!UICONTROL Data sources]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Manage]**。
1. 選取內建的Adobe Experience Platform資料來源。

   ![](../assets/journey23.png)

1. 在欄位群組中，檢查是否已選取下列欄位：

   * _人員>姓名>名字_
   * _人員>姓名>姓氏_
   * _人員>性別_
   * _個人電子郵件>地址_

1. 按一下「**[!UICONTROL Save]**」。

資料來源現在已設定完畢，且可供您在歷程中使用。
