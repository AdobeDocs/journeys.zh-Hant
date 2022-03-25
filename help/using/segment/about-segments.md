---
product: adobe campaign
title: 關於 Adobe Experience Platform 區段
description: 瞭解如何配置Adobe Experience Platform段
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: e5c0db2e1f85ea72fd54f91e4a26cc287377fb0e
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 2%

---

# 關於 Adobe Experience Platform 區段 {#about-segments}

如果你用的 [Adobe Experience Platform分段服務](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html) 建立段，可以利用 [!DNL Journey Orchestration]。 由於有專門的活動活動，您可以讓個人根據Adobe Experience Platform段的出入口進入或前進。 這還允許您使用簡單或高級表達式編輯器在行程中生成複雜條件。

假設您有「銀色客戶」部分。 通過本練習，您可以讓所有新的銀發客戶輸入行程併發送一系列個性化消息。 您還可以輕鬆地基於此段構建條件。

這裡有可能 [!DNL Journey Orchestration] 為您提供了分段：

* 訪問Adobe Experience Platform段清單。 請參閱 [建立段](../segment/creating-a-segment.md)。
* 直接在 [!DNL Journey Orchestration] 與使用分段服務建立它們的方法相同。 請參閱 [建立段](../segment/creating-a-segment.md)。
* 使用簡單或高級表達式編輯器在行程條件中利用段。 請參閱 [在條件中使用段](../segment/using-a-segment.md)。
* 添加 **[!UICONTROL Segment qualification]** 為了傾聽Adobe Experience Platform段的檔案出入口， 請參閱 [活動活動](../building-journeys/segment-qualification-events.md)。

## Journey Orchestration中的評價方法 {#evaluation-method-in-journey-orchestration}

在Journey Orchestration中，使用以下評估方法之一從段定義生成受眾：

* 流分段 — 段的受眾清單在新資料流入系統時即時保持最新。
* 批分段 — 段的受眾清單根據過去一小時內到達的資料按小時更新。

系統根據分段規則的複雜度和評估成本，對每個分段定義確定分批分段和流分段。

可查看中每個段的評估方法 **[!UICONTROL Evaluation method]** 的子菜單。

在您首次定義段後，配置檔案在符合條件時添加到受眾。

從先前資料中回填觀眾最多需要24小時。 在觀眾回填後，觀眾會不斷更新，隨時準備瞄準。