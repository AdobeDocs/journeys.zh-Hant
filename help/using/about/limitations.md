---
product: adobe campaign
solution: Journey Orchestration
title: 歷程協調限制
description: 進一步瞭解Journey Orchestration的限制
translation-type: tm+mt
source-git-commit: f562d4a967e6551d3b8a1bc4dbddbf01da9b3e70
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 2%

---


# 限制 {#limitations}

以下是與使用Journey Orchestration相關的限制。

## 一般動作限制

* 沒有發送限制。 
* 系統地在發生錯誤時執行兩次重試。 您無法根據收到的錯誤訊息調整重試次數。 
* 內建的&#x200B;**Reaction**&#x200B;事件可讓您對現成可用的動作做出反應（請參閱此[page](../building-journeys/reaction-events.md)）。 如果您想要回應透過自訂動作傳送的訊息，則必須設定專屬事件。 
* Adobe Campaign Classic分類整合不提供。

## 歷程版本限制{#journey-versions-limitations}

* 從v1中的事件活動開始的歷程，無法從其他版本中的事件以外的事件開始。 您無法以&#x200B;**區段資格**&#x200B;事件開始歷程。
* 從v1中的&#x200B;**區段資格**&#x200B;活動開始的旅程，必須始於後續版本的&#x200B;**區段資格**。
* 在&#x200B;**區段限定**（第一節點）中選擇的區段和命名空間無法在新版本中更改。
* 所有歷程版本的重新進入規則都必須相同。

## 區段資格{#segment-qualification}

* 由於吞吐量限制，**區段資格**&#x200B;活動無法與Adobe Campaign標準交易訊息搭配使用。 請參閱[Adobe Campaign標準產品說明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)。 
 

## 自訂動作限制

* 自訂動作URL不支援動態參數。 
* 僅支援POST和PUT呼叫方法。 
* 查詢參數或標題的名稱不能以&quot;。&quot;開頭。 或 &quot;$&quot;. 
* 不允許IP位址。 
* 內部Adobe位址(.adobe.) 不允許。
 

## Adobe Campaign動作限制

* Adobe Campaign Standard交易訊息在特定例項的各個通道中，每小時最多可傳送50 000則訊息。 請參閱[Adobe Campaign標準產品說明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)。 
 

## 事件限制

* 用於啟動客戶歷程的串流資料，必須先在Journey Orchestration中進行設定，才能取得獨特的協調ID。 此協調ID必須附加至即將傳入Adobe Experience Platform的串流負載。
 

## 資料來源限制

* 您可以在客戶歷程中運用外部資料來源，即時查閱外部資料。 這些來源必須可透過REST API使用、支援JSON並可處理大量請求。

## 從建立描述檔的同時開始的歷程記錄{#journeys-limitation-profile-creation}

在Adobe Experience Platform中建立／更新以API為基礎的描述檔時，會有延遲。 延遲方面的服務級別目標(SLT)從接收到統一配置檔案（請求的95個百分位數）&lt; 1分鐘，每秒20K請求(RPS)。

如果「歷程」同時觸發至描述檔建立，並立即從「描述檔服務」檢查／擷取資訊，則可能無法正常運作。

您可從以下兩種解決方案中選擇：

* 在第一個事件後新增等待活動，讓Adobe Experience Platform有必要在執行描述檔服務擷取時間。

* 設定不會立即運用個人檔案的歷程。 例如，如果歷程是設計來確認帳戶建立，體驗事件可能包含傳送第一個確認訊息（名字、姓氏、電子郵件地址等）所需的資訊。