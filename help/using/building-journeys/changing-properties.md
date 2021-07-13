---
product: adobe campaign
title: 變更屬性
description: 了解如何變更屬性
feature: 歷程
role: User
level: Intermediate
exl-id: 06d26078-b9b8-4dc4-918d-0f2426d00f54
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 0%

---

# 變更屬性 {#concept_prq_wqt_52b}

按一下右上角的鉛筆圖示，以存取歷程的屬性。

您可以變更歷程的名稱、新增說明、允許重新進入、選擇開始和結束日期，以及定義&#x200B;**[!UICONTROL Timeout and error]**&#x200B;持續時間（如果您是管理員）。

對於即時歷程，此畫面會顯示發佈日期以及發佈歷程的使用者名稱。

**複製技術詳細資訊**&#x200B;可讓您複製支援團隊可用於疑難排解的歷程相關技術資訊。 會複製下列資訊：JourneyVersion UID, OrgID, orgName, sandboxName, lastDeployedBy, lastDeployedAt。

![](../assets/journey32.png)

## 入口{#entrance}

依預設，新歷程允許重新進入。 您可以取消勾選「一次性」歷程的選項，例如當某人進入商店時，如果您想要提供一次性禮品。 在此情況下，您不會希望客戶能夠重新進入歷程並再次收到優惠方案。

歷程「結束」時，其狀態會是&#x200B;**[!UICONTROL Closed (no entrance)]**。 歷程將停止讓新人進入歷程。 已在歷程中的人員會正常完成歷程。

在30天的預設全域逾時後，歷程會切換為&#x200B;**已完成**&#x200B;狀態。 請參閱此[節](#global_timeout)。

## 歷程活動的逾時和錯誤 {#timeout_and_error}

編輯動作或條件活動時，您可以定義替代路徑以防發生錯誤或逾時。 如果詢問協力廠商系統的活動處理超過歷程屬性（**[!UICONTROL Timeout and  error]**&#x200B;欄位）中定義的逾時期間，則會選擇第二個路徑以執行潛在的備援動作。

授權值介於1到30秒之間。

如果您的歷程具有時效性，建議您定義非常短的&#x200B;**[!UICONTROL Timeout and error]**&#x200B;值(範例：回應人員的即時位置)，因為您無法將動作延遲超過幾秒。 如果您的歷程不太時間敏感，您可以使用較長的值，讓系統有更多時間呼叫以傳送有效的回應。

[!DNL Journey Orchestration] 也會使用全域逾時。請參閱[下一節](#global_timeout)。

## 全域歷程逾時 {#global_timeout}

除了歷程活動中使用的[timeout](#timeout_and_error)，還有全域歷程逾時（不會顯示在介面中且無法變更）。 此逾時會在個人進入後30天停止歷程中的進度。 這表示個人的歷程不能持續超過30天。 在30天逾時期間後，會刪除個人的資料。 在逾時期間結束時仍在歷程中流動的個人將會停止，並會將其視為報表中的錯誤列入考量。

>[!NOTE]
>
>[!DNL Journey Orchestration] 不會直接對隱私權選擇退出、存取或刪除請求做出反應。不過，全域逾時可確保個人在任何歷程中不會停留超過30天。

由於30天的歷程逾時，當不允許歷程重新進入時，我們無法確定重新進入封鎖的作用超過30天。 事實上，由於我們刪除了有關在他們進入30天後進入歷程的所有資訊，因此我們無法知道在超過30天前進入的人。

## 時區和設定檔時區 {#timezone}

時區是在歷程層級定義。

您可以輸入固定時區，或使用Adobe Experience Platform設定檔來定義歷程時區。

有關時區管理的詳細資訊，請參閱本頁](../building-journeys/timezone-management.md)。[
