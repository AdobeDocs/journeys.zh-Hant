---
title: 設定資料來源
description: 瞭解如何針對歷程中的簡單使用案例設定資料來源
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 6%

---


# 設定資料來源{#concept_ax3_bcy_w2b}

在我們的使用案例中，我們想要將個人化資料用於我們的訊息。 我們還需要檢查一下這個人是女人。 此資訊會儲存在即時客戶個人檔案資料庫中。 技 **術使用者** ，必須檢查這些欄位是否已在內建的Adobe Experience Platform資料來源中定義。

有關資料源配置的其他資訊，請參閱 [](../datasource/about-data-sources.md)。

1. 在頂端功能表中，按一 **[!UICONTROL Data Sources]** 下標籤並選取內建的Adobe Experience Platform資料來源。

   ![](../assets/journey23.png)

1. 在欄位群組中，檢查下列欄位是否已選取：

   * _person > name > firstName_
   * _person > name > lastName_
   * _人員>性別_
   * _個人電子郵件>地址_

1. 按一下「**[!UICONTROL Save]**」。

資料來源現在已設定好，可供您在歷程中使用。
