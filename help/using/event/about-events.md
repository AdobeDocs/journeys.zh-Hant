---
title: 關於事件
description: 瞭解如何設定事件
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
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1

---


# 關於事件 {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="關於事件"
>abstract="事件會連結至人員。 它與人的行為有關（例如，某人購買產品、造訪商店、退出網站等）或是某個人所發生的事（例如，一個人達到10,000個忠誠點）。 這是Journey Orchestration在歷程中所聽到的，以協調下一個最佳動作。"

事件會連結至人員。 它與人的行為有關（例如，某人購買產品、造訪商店、退出網站等）或是某個人所發生的事（例如，一個人達到10,000個忠誠點）。 這是Journey Orchestration在歷程中所聽到的，以協調下一個最佳動作。

此組態是必 **備的**，因為Journey Orchestration是設計來監聽活動，而且一律由技術使用者 **執行**。

事件配置允許您定義「歷程協調」將接收的資訊作為事件。 您可以使用數個事件（在旅程的不同步驟中），而數個歷程可以使用同一個事件。

如果您編輯草稿或即時歷程中使用的事件，則只能變更名稱、說明或新增裝載欄位。 我們嚴格限制草稿或即時歷程版本，以避免中斷歷程。

## 一般原則 {#section_r1f_xqt_pgb}

事件是POST API呼叫。 事件會透過串流擷取API傳送至Adobe Experience Cloud Data Platform。 透過交易傳訊API傳送之事件的URL目的地稱為「入口」。 事件的裝載遵循XDM格式。

淨荷包含串流擷取API運作所需的資訊（在標題中），以及歷程協調所需的資訊（事件ID、淨荷主體的一部分），以及歷程（在主體中，例如放棄的購物車數量）。 串流擷取有兩種模式：驗證和未驗證。 如需串流擷取API的詳細資訊，請參 [閱此連結](https://docs.adobe.com/content/help/en/experience-platform/xdm/api/getting-started.html)。

在透過串流擷取API到達後，事件會流入名為Pipeline的內部服務，然後流入資料平台。 如果事件結構描述已啟用「即時客戶描述檔服務」標幟，且資料集ID也具有「即時客戶描述檔」標幟，則會流入「即時客戶描述檔服務」。

Pipeline會篩選由Journey Orchestration提供且包含事件裝載的裝載，其中包含Journey Orchestration eventIDs（請參閱下方的事件建立程式）的事件。 這些活動會由歷程協調(Journey Orchestration)來聆聽，並觸發相應的歷程。

## 建立新事件 {#section_tbk_5qt_pgb}

以下是設定新事件的主要步驟：

1. 在頂端功能表中，按一下標籤 **[!UICONTROL Events]** 上。 將顯示事件清單。 有關 [](../about/user-interface.md) 介面的詳細資訊，請參閱。

   ![](../assets/journey5.png)

1. 按一 **[!UICONTROL Add]** 下以建立新事件。 事件配置窗格在螢幕的右側開啟。

   ![](../assets/journey6.png)

1. 輸入事件的名稱。

   >[!NOTE]
   >
   >請勿使用空格或特殊字元。 請勿使用超過30個字元。

1. 新增說明至您的活動。 此步驟為可選步驟。
1. 定義架構和裝載欄位：在這裡，您可以選擇Journey Orchestration預期會收到的活動資訊（通常稱為負載）。 然後，您就可以在您的旅程中使用這項資訊。 參見[](../event/defining-the-payload-fields.md)。
1. 使用此事件的歷程次數會顯示在欄位 **[!UICONTROL Used in]** 中。 您可以按一下 **[!UICONTROL View journeys]** 圖示，顯示使用此事件的歷程清單。
1. 新增命名空間。 此步驟為可選步驟，但建議您新增命名空間，以便您運用即時客戶個人檔案服務中儲存的資訊。 它定義事件具有的密鑰類型。 參見[](../event/selecting-the-namespace.md)。
1. 定義索引鍵：從裝載欄位選擇欄位，或定義公式以識別與事件關聯的人員。 如果您選取命名空間，此索引鍵會自動設定（但仍可編輯）。 事實上，Journey Orchestration會挑選應該對應於命名空間的索引鍵（例如，如果您選取電子郵件命名空間，則會選取電子郵件索引鍵）。 參見[](../event/defining-the-event-key.md)。
1. 新增條件。 此步驟為可選步驟。 這可讓系統僅處理符合條件的事件。 條件只能根據事件中包含的資訊。 參見[](../event/adding-a-condition.md)。
1. 按一下 **[!UICONTROL Save]**.

   ![](../assets/journey7.png)

   現在已設定活動，並準備放入歷程中。 接收事件需要其他設定步驟。 參見[](../event/additional-steps-to-send-events-to-journey-orchestration.md)。
