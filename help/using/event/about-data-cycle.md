---
product: adobe campaign
solution: Journey Orchestration
title: 事件資料週期
description: 瞭解事件資料週期
feature: 旅程
role: 業務從業人員
level: 中級
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 78%

---


# 資料週期 {#section_r1f_xqt_pgb}

事件屬於 POST API 呼叫。事件會透過串流獲取 API 傳送至 Adobe Experience Platform。透過交易訊息 API 傳送的事件 URL 目的地稱為「入口」。事件的有效負載遵從 XDM 格式。

有效負載包含串流獲取 API 運作（在標題中）的所需資訊，以及 [!DNL Journey Orchestration] 運作（事件 ID、有效負載正文的一部分）所需的資訊，以及用於歷程（在正文中，例如捨棄購物車的金額）的資訊。串流獲取共有兩種模式，分別是驗證和未驗證。如需串流獲取 API 的詳細資訊，請參閱[此連結](https://docs.adobe.com/content/help/zh-Hant/experience-platform/xdm/api/getting-started.html)。

在透過串流獲取 API 到達目的地之後，事件會流入名為 Pipeline 的內部服務，再流入 Adobe Experience Platform。如果事件結構已啟用「即時客戶個人檔案服務」標幟，且資料集 ID 也具有「即時客戶個人檔案」標幟，就會流入「即時客戶個人檔案服務」。

對於系統產生的事件，Pipeline會篩選包含[!DNL Journey Orchestration] eventIDs的裝載（請參閱下面的事件建立程式）的事件，這些事件由[!DNL Journey Orchestration]提供並包含在事件裝載中。 對於規則型事件，系統會使用eventID條件來識別事件。 這些事件會由 [!DNL Journey Orchestration] 監聽，並會觸發相對應的歷程。
