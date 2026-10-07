---
product: adobe campaign
title: 事件資料週期
description: 瞭解事件資料週期
feature: Journeys
role: User
level: Intermediate
exl-id: b362589a-32b0-4dbd-8ceb-a371e1e048ac
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
source-wordcount: '232'
ht-degree: 79%
---
# 資料週期 {#section_r1f_xqt_pgb}

事件屬於 POST API 呼叫。 事件會透過串流獲取 API 傳送至 Adobe Experience Platform。 透過交易訊息 API 傳送的事件 URL 目的地稱為「入口」。 事件的有效負載遵從 XDM 格式。

有效負載包含串流獲取 API 運作（在標題中）的所需資訊，以及 [!DNL Journey Orchestration] 運作（事件 ID、有效負載正文的一部分）所需的資訊，以及用於歷程（在正文中，例如捨棄購物車的金額）的資訊。 串流攝取共有兩種模式，分別是已驗證和未驗證。 如需串流獲取 API 的詳細資訊，請參閱[此連結](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=zh-Hant)。

在透過串流獲取 API 到達目的地之後，事件會流入名為管道的內部服務，再流入 Adobe Experience Platform。 如果事件結構描述已啟用「即時客戶輪廓服務」標幟，且資料集 ID 也具有「即時客戶輪廓」標幟，就會流入「即時客戶輪廓服務」。

對於系統產生的事件，Pipeline會篩選由[!DNL Journey Orchestration]提供且包含[!DNL Journey Orchestration]個eventID之裝載（請參閱下方的事件建立程式）的事件。 對於規則型事件，系統會使用eventID條件來識別事件。 這些事件會由 [!DNL Journey Orchestration] 監聽，並會觸發相對應的歷程。
