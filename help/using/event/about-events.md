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
translation-type: ht
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1
workflow-type: ht
source-wordcount: '735'
ht-degree: 100%

---


# 關於事件{#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="關於事件"
>abstract="事件會連結至人員，它與人的行為相關 (例如，某人購買產品、造訪商店、離開網站等等)或是某人發生的事 (例如，某人達到 10,000 點忠誠點數)。這是 Journey Orchestration 在歷程中會監聽的事件，以便協調下一個最佳動作。"

事件會連結至人員，它與人的行為相關 (例如，某人購買產品、造訪商店、離開網站等等)或是某人發生的事 (例如，某人達到 10,000 點忠誠點數)。這是 Journey Orchestration 在歷程中會監聽的事件，以便協調下一個最佳動作。

此設定是&#x200B;**強制性**&#x200B;的，因為 Journey Orchestration 的設計旨在監聽事件，且一律會由&#x200B;**技術使用者**&#x200B;執行。

事件設定可讓您定義 Journey Orchestration 接收做為事件的資訊。您可以使用數個事件 (在歷程的不同步驟中)，而數個歷程則可以使用同一個事件。

如果您編輯草稿或即時歷程中使用的事件，則只能變更名稱和說明，或是新增裝載欄位。我們對草稿或即時歷程版本有嚴格限制，以免中斷歷程。

## 一般原則{#section_r1f_xqt_pgb}

事件屬於 POST API 呼叫。事件會透過串流擷取 API 傳送至 Adobe Experience Cloud Data Platform。透過交易訊息 API 傳送的事件 URL 目的地稱為「入口」。事件的裝載遵從 XDM 格式。

裝載包含了串流擷取 API 運作 (在標題中) 所需的資訊，以及 Journey Orchestration 運作 (事件 ID、裝載正文的一部分) 所需的資訊，還有用於歷程 (在正文中，例如捨棄購物車的金額) 的資訊。串流擷取共有兩種模式，分別是驗證和未驗證。如需串流擷取 API 的詳細資訊，請參閱[此連結](https://docs.adobe.com/content/help/zh-Hant/experience-platform/xdm/api/getting-started.html)。

在透過串流擷取 API 到達目的地之後，事件會流入名為 Pipeline 的內部服務，再流入 Data Platform。如果事件結構已啟用「即時客戶個人檔案服務」標幟，且資料集 ID 也具有「即時客戶個人檔案」標幟，就會流入「即時客戶個人檔案服務」。

Pipeline 會篩選由 Journey Orchestration 提供且包含 Journey Orchestration eventID 之裝載 (請參見下方的事件建立流程) 的事件。這些事件會由 Journey Orchestration 監聽，並會觸發相應的歷程。

## 建立新事件{#section_tbk_5qt_pgb}

以下是設定新事件的主要步驟：

1. 在頂端選單中，按一下「**[!UICONTROL Events]**」標籤。畫面隨即顯示事件清單。請參見[](../about/user-interface.md)以瞭解介面的詳細資訊。

   ![](../assets/journey5.png)

1. 按一下「**[!UICONTROL Add]**」以建立新事件。事件設定窗格會在畫面右側開啟。

   ![](../assets/journey6.png)

1. 輸入事件的名稱。

   >[!NOTE]
   >
   >請勿使用空格或特殊字元。請勿使用超過 30 個字元。

1. 新增說明至您的事件。此步驟為選填。
1. 定義結構和裝載欄位：您可以在此處選取 Journey Orchestration 預期會收到的事件資訊 (通常稱為裝載）。接著，您就可以在您的歷程中使用這項資訊。請參見[](../event/defining-the-payload-fields.md)。
1. 使用此事件的歷程次數會顯示在「**[!UICONTROL Used in]**」欄位中。您可以按一下 **[!UICONTROL View journeys]**&#x200B;圖示，以顯示使用此事件的歷程清單。
1. 新增命名空間。此步驟為選填，但建議您新增命名空間，以便運用儲存在「即時客戶個人檔案服務」的資訊。它會定義事件具備的金鑰類型。請參見[](../event/selecting-the-namespace.md)。
1. 定義金鑰：從您的裝載欄位選擇一個欄位，或是定義一個公式以識別與事件相關聯的人員。如果您選取命名空間，系統便會自動設定此金鑰 (但您仍可加以編輯)。事實上，Journey Orchestration 會挑選應該與命名空間對應的金鑰 (例如，如果您選取電子郵件命名空間，系統便會選取電子郵件金鑰）。請參見[](../event/defining-the-event-key.md)。
1. 新增條件。此步驟為選填。這可讓系統僅處理符合條件的事件。您只能根據事件含有之資訊設定條件。請參見[](../event/adding-a-condition.md)。
1. 按一下「**[!UICONTROL Save]**」。

   ![](../assets/journey7.png)

   條件現在已設定完畢，且準備好放入歷程中。若要接收事件，則需要完成其他設定步驟。請參見[](../event/additional-steps-to-send-events-to-journey-orchestration.md)。
