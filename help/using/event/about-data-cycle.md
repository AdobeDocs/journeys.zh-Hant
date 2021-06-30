---
product: adobe campaign
title: 事件資料週期
description: 了解事件資料週期
feature: 歷程
role: Business Practitioner
level: Intermediate
exl-id: b362589a-32b0-4dbd-8ceb-a371e1e048ac
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 76%

---

# 資料週期 {#section_r1f_xqt_pgb}

事件屬於 POST API 呼叫。事件會透過串流獲取 API 傳送至 Adobe Experience Platform。透過交易訊息 API 傳送的事件 URL 目的地稱為「入口」。事件的有效負載遵從 XDM 格式。

有效負載包含串流獲取 API 運作（在標題中）的所需資訊，以及 [!DNL Journey Orchestration] 運作（事件 ID、有效負載正文的一部分）所需的資訊，以及用於歷程（在正文中，例如捨棄購物車的金額）的資訊。串流獲取共有兩種模式，分別是驗證和未驗證。如需串流獲取 API 的詳細資訊，請參閱[此連結](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html)。

在透過串流獲取 API 到達目的地之後，事件會流入名為 Pipeline 的內部服務，再流入 Adobe Experience Platform。如果事件結構已啟用「即時客戶個人檔案服務」標幟，且資料集 ID 也具有「即時客戶個人檔案」標幟，就會流入「即時客戶個人檔案服務」。

對於系統產生的事件，Pipeline會篩選由[!DNL Journey Orchestration]提供且包含[!DNL Journey Orchestration] eventID之有效負載（請參閱下方的事件建立程式）的事件。 對於規則型事件，系統會使用eventID條件來識別事件。 這些事件會由 [!DNL Journey Orchestration] 監聽，並會觸發相對應的歷程。
