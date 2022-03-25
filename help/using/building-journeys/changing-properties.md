---
product: adobe campaign
title: 變更屬性
description: 瞭解如何更改屬性
feature: Journeys
role: User
level: Intermediate
exl-id: 06d26078-b9b8-4dc4-918d-0f2426d00f54
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 0%

---

# 變更屬性 {#concept_prq_wqt_52b}

按一下右上角的鉛筆表徵圖以訪問行程的屬性。

您可以更改行程名稱、添加說明、允許重新進入、選擇起始日期和終止日期並定義 **[!UICONTROL Timeout and error]** 持續時間（如果您是管理員）。

對於即時行程，此螢幕顯示發佈日期和發佈行程的用戶的名稱。

的 **複製技術詳細資訊** 允許您複製支援團隊用於故障排除的旅程的技術資訊。 將複製以下資訊：JourneyVersion UID、OrgID、orgName、sandboxName、lastDeployedBy、lastDeployedAt。

![](../assets/journey32.png)

## 入口{#entrance}

預設情況下，新旅程允許重新進入。 您可以取消選中「一次性」旅程選項，例如，如果您想在人員進入商店時提供一次性禮物。 在這種情況下，您不希望客戶能夠重新進入行程並再次收到優惠。

當旅程「結束」時，它將具有 **[!UICONTROL Closed (no entrance)]**。 旅程將停止讓新人進入旅程。 已經在旅途中的人將正常完成旅程。

在預設全局超時30天後，該行程將切換到 **已完成** 狀態。 查看 [節](#global_timeout)。

## 行程活動超時和出錯 {#timeout_and_error}

編輯操作或條件活動時，您可以在出現錯誤或超時時定義替代路徑。 如果查詢第三方系統的活動的處理超過行程的屬性中定義的超時持續時間(**[!UICONTROL Timeout and  error]** 欄位)，將選擇第二個路徑以執行可能的回退操作。

授權值介於1到30秒之間。

我們建議你定義一個 **[!UICONTROL Timeout and error]** 值（如果您的行程是時間敏感型的）(例如：對人的即時位置進行響應)，因為您不能將操作延遲超過幾秒鐘。 如果您的行程對時間不太敏感，則可以使用較長的值為調用的系統提供更多時間，以發送有效響應。

[!DNL Journey Orchestration] 還使用全局超時。 查看 [下一部分](#global_timeout)。

## 全局行程超時 {#global_timeout}

除 [超時](#timeout_and_error) 在行程活動中使用，還有一個全局行程超時，該超時不顯示在介面中，無法更改。 此超時將阻止個人在進入後30天內的進度。 這意味著一個人的旅程不能超過30天。 在30天超時期後，將刪除個人的資料。 在超時期結束時仍在旅途中流動的個人將被停止，並將他們作為報告錯誤加以考慮。

>[!NOTE]
>
>[!DNL Journey Orchestration] 不會直接對隱私選擇退出、訪問或刪除請求做出反應。 但是，全局超時可確保個人在任何行程中停留的時間不超過30天。

由於30天的行程超時，當不允許再入行程時，無法確保再入阻塞工作超過30天。 事實上，當我們刪除有關在他們進入旅程30天後進入旅程的所有資訊時，我們無法知道之前在30多天前輸入的人。

## 時區和配置檔案時區 {#timezone}

時區在行程級別定義。

您可以輸入固定時區或使用Adobe Experience Platform配置檔案定義行程時區。

有關時區管理的詳細資訊，請參見 [此頁](../building-journeys/timezone-management.md)。
