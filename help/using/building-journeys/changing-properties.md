---
product: adobe campaign
solution: Journey Orchestration
title: 變更屬性
description: 瞭解如何變更屬性
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 0%

---



# 變更屬性 {#concept_prq_wqt_52b}

按一下右上角的鉛筆圖示，以存取歷程的屬性。

您可以變更旅程的名稱、新增說明、允許重新進入、選擇開始和結束日期，並定義&#x200B;**[!UICONTROL Timeout and error]**&#x200B;持續時間（如果您是管理員）。

![](../assets/journey32.png)

## 入口{#entrance}

依預設，新的旅程允許重新進入。 您可以取消勾選「單拍」歷程的選項，例如，當某人進入商店時，您想要提供一次性禮品。 在這種情況下，您不希望客戶能夠重新進入歷程並再次收到優惠。

當旅程「結束」時，狀態為&#x200B;**[!UICONTROL Closed (no entrance)]**。 這段旅程將不再讓新人進入這段旅程。 已經在旅途中的人將正常完成旅程。

## 歷程活動的逾時和錯誤{#timeout_and_error}

在編輯動作或條件活動時，您可以定義替代路徑，以防發生錯誤或逾時。 如果詢問第三方系統的活動的處理超過在歷程的屬性（**[!UICONTROL Timeout and  error]**&#x200B;欄位）中定義的超時持續時間，則選擇第二路徑以執行潛在的備援動作。

授權值介於1到30秒之間。

如果您的歷程對時間很敏感，建議您定義非常短的&#x200B;**[!UICONTROL Timeout and error]**&#x200B;值(例如：回應人員的即時位置)，因為您無法將動作延遲超過幾秒。 如果您的歷程對時間不太敏感，您可以使用較長的值，為呼叫傳送有效回應的系統提供更多時間。

[!DNL Journey Orchestration] 也使用全域逾時。請參閱[下一節](#global_timeout)。

## 全域歷程逾時{#global_timeout}

除了在歷程活動中使用的[timeout](#timeout_and_error)之外，還有一個全局歷程超時，該超時不會顯示在介面中，也不能更改。 此逾時會在個人進入後30天內停止歷程中的進度。 這表示個人的旅程不能超過30天。 在30天逾時期間後，會刪除個人的資料。 在逾時期間結束時仍在行程中流動的個人將停止，並將其視為報告中的錯誤。

>[!NOTE]
>
>[!DNL Journey Orchestration] 不會直接回應隱私權選擇退出、存取或刪除要求。不過，全域逾時可確保個人在任何行程中不會停留超過30天。

由於30天的行程逾時，當行程重新進入不允許時，我們無法確保重新進入的阻擋作用超過30天。 事實上，由於我們刪除了所有有關在他們進入旅程30天後進入旅程的資訊，因此我們無法知道在30天前進入的人。

## 時區和描述檔時區{#timezone}

時區是在歷程層級定義。

您可以輸入固定時區或使用Adobe Experience Platform設定檔來定義旅程時區。

有關時區管理的詳細資訊，請參見[本頁](../building-journeys/timezone-management.md)。
