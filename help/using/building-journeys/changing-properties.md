---
product: adobe campaign
title: 變更屬性
description: 瞭解如何變更屬性
feature: Journeys
role: User
level: Intermediate
exl-id: 06d26078-b9b8-4dc4-918d-0f2426d00f54
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 2%

---

# 變更屬性 {#concept_prq_wqt_52b}



>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_


按一下右上角的鉛筆圖示以存取歷程的屬性。

如果您是管理員，可以變更歷程名稱、新增說明、允許重新進入、選擇開始和結束日期並定義&#x200B;**[!UICONTROL Timeout and error]**&#x200B;持續時間。

若為即時歷程，此畫面會顯示發佈日期和發佈歷程的使用者名稱。

**複製技術詳細資料**&#x200B;可讓您複製支援團隊可用於疑難排解的歷程相關技術資訊。 已複製下列資訊：JourneyVersion UID、OrgID、orgName、sandboxName、lastDeployedBy、lastDeployedAt。

![](../assets/journey32.png)

## 入口{#entrance}

預設情況下，新歷程允許重新進入。您可以取消勾選「單次」歷程的選項，例如，如果您想要在某人進入商店時提供一次性禮物。 在這種情況下，您不希望客戶能夠重新進入歷程並再次收到選件。

歷程「結束」時，其狀態會是&#x200B;**[!UICONTROL Closed (no entrance)]**。 歷程將停止讓新個人進入歷程。 已在歷程中的人員將正常完成歷程。

在預設全域逾時30天後，歷程將切換為&#x200B;**已完成**&#x200B;狀態。 請參閱[本章節](#global_timeout)。

## 歷程活動中的逾時和錯誤 {#timeout_and_error}

編輯動作或條件活動時，您可以定義替代路徑，以防錯誤或逾時。 如果處理詢問協力廠商系統的活動超過歷程屬性（**[!UICONTROL Timeout and  error]**&#x200B;欄位）中定義的逾時期間，將會選擇第二個路徑來執行可能的遞補動作。

授權值介於1到30秒之間。

如果您的歷程有時效性（例如：對人員的即時位置有所反應），建議您定義非常短的&#x200B;**[!UICONTROL Timeout and error]**&#x200B;值，因為您的動作不能延遲超過幾秒鐘。 如果您的歷程較不有時效性，您可以使用較長的值，讓系統有更多時間呼叫，以傳送有效回應。

[!DNL Journey Orchestration]也使用全域逾時。 請參閱[下一節](#global_timeout)。

## 全域歷程逾時 {#global_timeout}

除了歷程活動中使用的[逾時](#timeout_and_error)之外，還有未顯示在介面中且無法變更的全域歷程逾時。 此逾時將會在個人進入後30天內，停止該歷程中的個人進度。 這表示個人的歷程不能持續超過30天。 在30天逾時期間後，個人的資料會遭到刪除。 在逾時期間結束時仍在歷程中流動的個人將會停止，且他們將被視為報告中的錯誤。

>[!NOTE]
>
>[!DNL Journey Orchestration]不會直接回應隱私權選擇退出、存取或刪除請求。 不過，全域逾時可確保個人在任何歷程中的逗留時間不會超過30天。

由於30天歷程逾時，當歷程不允許重新進入時，我們無法確保重新進入封鎖將超過30天。 事實上，當我們移除在進入歷程30天後進入歷程之人員的所有相關資訊時，我們無法得知該人員先前已進入（超過30天前）。

## 時區和設定檔時區 {#timezone}

時區是在歷程層級定義。

您可以輸入固定時區，或使用Adobe Experience Platform設定檔來定義歷程時區。

如需時區管理的詳細資訊，請參閱[此頁面](../building-journeys/timezone-management.md)。
