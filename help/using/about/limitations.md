---
product: adobe campaign
title: Journey Orchestration限制
description: 瞭解有關Journey Orchestration限制的更多資訊
feature: Journeys
role: User
level: Beginner
exl-id: fef039ae-c04d-4198-a082-4be27710255f
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 2%

---

# 限制 {#limitations}

以下是與使用Journey Orchestration有關的限制。

## 一般操作限制

* 沒有發送限制。 
* 在出現錯誤時系統地執行三次重試。 無法根據收到的錯誤消息調整重試次數。 
* 內置 **反應** 事件允許您對現成操作做出反應(請參閱 [頁](../building-journeys/reaction-events.md))。 如果要對通過自定義操作發送的消息做出反應，則需要配置專用事件。 

## 行程版本限制 {#journey-versions-limitations}

* 從v1中的事件活動開始的行程不能從其他版本中的事件以外的內容開始。 您不能以 **段資格** 的子菜單。
* 從 **段資格** v1中的活動必須始終以 **段資格** 版。
* 中選擇的段和命名空間 **分部資格** （第一個節點）在新版本中無法更改。
* 在所有行程版本中，重入規則必須相同。

## 區段資格 {#segment-qualification}

* 的 **分部資格** 由於吞吐量限制，活動不能與Adobe Campaign Standard事務性消息傳遞一起使用。 請參閱 [Adobe Campaign Standard產品說明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)。 
 

## 自定義操作限制

* 自定義操作URL不支援動態參數。 
* 僅支援POST和PUT調用方法。 
* 查詢參數或標頭的名稱不能以「」開頭。 或 &quot;$&quot;. 
* 不允許使用IP地址。 
* 內部Adobe地址(.adobe.) 不允許。
 

## Adobe Campaign行為限制

* Adobe Campaign Standard事務性消息傳遞在給定實例的每個通道中每小時最多有50 000條消息。 請參閱 [Adobe Campaign Standard產品說明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)。 
 

## 事件限制

* 對於系統生成的事件，必須首先在Journey Orchestration中配置用於啟動客戶行程的流資料，以獲取唯一的業務流程ID。 此業務流程ID必須附加到流負載中進入Adobe Experience Platform。 此限制不適用於基於規則的事件。
 

## 資料源限制

* 在客戶行程中，可利用外部資料源即時查找外部資料。 這些源必須可通過REST API使用，支援JSON並能夠處理請求量。

## 與建立配置檔案同時開始的行程 {#journeys-limitation-profile-creation}

在Adobe Experience Platform，存在與基於API的配置檔案建立/更新相關的延遲。 在每秒20K請求(RPS)的卷上，從接收到統一配置檔案的服務級別目標(SLT)的延遲小於95%請求數的1分鐘。

如果同時觸發「行程」以建立配置檔案，並立即從「配置檔案服務」中檢查/檢索資訊，則它可能無法正常工作。

您可以從以下兩種解決方案中選擇一種：

* 在第一個事件後添加等待活動，為Adobe Experience Platform提供執行接收配置檔案服務所需的時間。

* 設定不立即利用配置檔案的行程。 例如，如果行程旨在確認帳戶建立，則體驗事件可能包含發送第一個確認消息（名字、姓氏、電子郵件地址等）所需的資訊。
