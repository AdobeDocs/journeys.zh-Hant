---
product: adobe campaign
solution: Journey Orchestration
title: Journey Orchestration限制
description: 進一步瞭解Journey Orchestration限制
feature: Journeys
role: Business Practitioner
level: Beginner
translation-type: tm+mt
source-git-commit: 8685dfdcbfb414af89b304a6a9a0f9418959909b
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 2%

---


# 限制 {#limitations}

以下是與使用Journey Orchestration相關的限制。

## 一般動作限制

* 沒有發送限制。 
* 系統地在發生錯誤時執行兩次重試。 您無法根據收到的錯誤訊息調整重試次數。 
* 內建的&#x200B;**Reaction**&#x200B;事件可讓您對現成可用的動作做出反應（請參閱此[page](../building-journeys/reaction-events.md)）。 如果您想要回應透過自訂動作傳送的訊息，則必須設定專屬事件。 
* 沒有Adobe Campaign Classic分類整合。

## 歷程版本限制{#journey-versions-limitations}

* 從v1中的事件活動開始的歷程，無法從其他版本中的事件以外的事件開始。 您無法以&#x200B;**區段資格**&#x200B;事件開始歷程。
* 從v1中的&#x200B;**區段資格**&#x200B;活動開始的旅程，必須始於後續版本的&#x200B;**區段資格**。
* 在&#x200B;**區段限定**（第一節點）中選擇的區段和命名空間無法在新版本中更改。
* 所有歷程版本的重新進入規則都必須相同。

## 區段資格{#segment-qualification}

* 由於吞吐量限制，**段限定**&#x200B;活動不能與「Adobe Campaign Standard事務性消息」一起使用。 請參閱[Adobe Campaign Standard產品說明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)。 
 

## 自訂動作限制

* 自訂動作URL不支援動態參數。 
* 僅支援POST和PUT呼叫方法。 
* 查詢參數或標題的名稱不能以&quot;。&quot;開頭。 或 &quot;$&quot;. 
* 不允許IP位址。 
* 內部Adobe位址(.adobe.) 不允許。
 

## Adobe Campaign行動限制

* Adobe Campaign Standard事務性消息傳遞在特定實例的各個通道中，每小時最多50 000條消息。 請參閱[Adobe Campaign Standard產品說明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)。 
 

## 事件限制

* 對於系統產生的事件，必須先在Journey Orchestration中設定用於啟動客戶歷程的串流資料，才能取得唯一的協調ID。 此協調ID必須附加至傳入Adobe Experience Platform的串流負載。 此限制不適用於規則型事件。
 

## 資料來源限制

* 您可以在客戶歷程中運用外部資料來源，即時查閱外部資料。 這些來源必須可透過REST API使用、支援JSON並可處理大量請求。

## 從建立描述檔的同時開始的歷程記錄{#journeys-limitation-profile-creation}

在Adobe Experience Platform，基於API的配置檔案建立／更新存在延遲。 延遲方面的服務級別目標(SLT)從接收到統一配置檔案（請求的95個百分位數）&lt; 1分鐘，每秒20K請求(RPS)。

如果「歷程」同時觸發至描述檔建立，並立即從「描述檔服務」檢查／擷取資訊，則可能無法正常運作。

您可從以下兩種解決方案中選擇：

* 在第一個事件後添加等待活動，為Adobe Experience Platform提供執行Profile Service接收所需的時間。

* 設定不會立即運用個人檔案的歷程。 例如，如果歷程是設計來確認帳戶建立，體驗事件可能包含傳送第一個確認訊息（名字、姓氏、電子郵件地址等）所需的資訊。