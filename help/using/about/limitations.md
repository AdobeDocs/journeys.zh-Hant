---
product: adobe campaign
title: Journey Orchestration限制
description: 深入了解Journey Orchestration限制
feature: Journeys
role: User
level: Beginner
exl-id: fef039ae-c04d-4198-a082-4be27710255f
source-git-commit: 18c94897b5cea0d92a83f36845fdda64220b668f
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 42%

---

# 限制 {#limitations}

以下是與使用Journey Orchestration相關的限制。

## 一般歷程護欄 {#journeys-guardrails-journeys}

* 歷程中的活動數上限為50。 活動數會顯示在歷程畫布的左上方區段。
* 數量 **即時歷程** 在一個組織中，每個沙箱最多只能有100個。 達到此限制時，您無法再發佈新的歷程。

## 一般動作限制

* 沒有傳送限制。 
* 如果出現錯誤，將系統地執行三次重試。您無法根據收到的錯誤訊息調整重試次數。 
* 內建 **反應** 事件可讓您對現成可用的動作做出反應(請參閱 [頁面](../building-journeys/reaction-events.md))。 如果您想對透過自訂動作傳送的訊息做出反應，需要設定專用事件。 

## 歷程版本限制 {#journey-versions-limitations}

* 從 v1 中的事件活動開始的歷程無法從其他版本中的事件開始。您無法透過&#x200B;**區段資格**&#x200B;事件開始歷程。
* 在 v1 中，以&#x200B;**區段資格**&#x200B;活動開始的歷程在後續版本中必須一律以&#x200B;**區段資格**&#x200B;開始。
* 在 **區段資格** （第一個節點）在新版本中無法變更。
* 所有歷程版本中的重新進入規則必須相同。

## 區段資格 {#segment-qualification}

* 此 **區段資格** 由於輸送量限制，活動無法與Adobe Campaign Standard交易式訊息搭配使用。 請參閱 [Adobe Campaign Standard產品說明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 

## 自訂動作限制

* 自訂動作 URL 不支援動態參數。 
* 僅支援 POST 和 PUT 呼叫方法. 
* 查詢參數或標題的名稱不得以「.」開頭 或 &quot;$&quot;。 
* 不允許使用 IP 位址. 
* 內部 Adobe 位址 (.adobe.) 是不允許的。 

## Adobe Campaign動作限制

* Adobe Campaign Standard交易式訊息在指定執行個體的各個通道上每小時有50,000則訊息。 請參閱 [Adobe Campaign Standard產品說明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 

## 事件限制

* 對於系統產生的事件，必須先在Journey Orchestration中設定用來起始客戶歷程的串流資料，才能取得唯一的協調ID。 此協調ID必須附加至傳入Adobe Experience Platform的串流裝載。 此限制不適用於規則型事件。 

## 資料來源限制

* 可在客戶歷程中運用外部資料來源，即時查閱外部資料。 這些來源必須可透過REST API使用、支援JSON並且能夠處理請求量。

## 從建立設定檔的同時開始的歷程 {#journeys-limitation-profile-creation}

在 Adobe Experience Platform 中建立/更新以 API 為基礎的設定檔會有延遲。對於第 95 個百分位數的請求，服務層級目標 (SLT) 從接收到統一設定檔的延遲時間小於 1 分鐘，每秒請求量為 20K (RPS)。

如果歷程同時觸發至設定檔建立，並立即從設定檔服務檢查/擷取資訊，則可能無法正常運作。

您可以從以下兩種解決方案中選擇一種：

* 在第一個事件後新增等待活動，為 Adobe Experience Platform 提供執行擷取至設定檔服務所需的時間。

* 設定不會立即運用設定檔的歷程。 例如，如果歷程的設計是要確認帳戶的建立，則體驗事件可能包含傳送第一個確認訊息（名字、姓氏、電子郵件地址等）所需的資訊。
