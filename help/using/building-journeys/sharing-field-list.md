---
title: 步驟事件欄位清單
description: 步驟事件欄位清單
feature: Journeys
topic: Content Management
role: User
level: Intermediate
source-git-commit: 2195ee3863b38ead504eb6785ceb3c37735fade9
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 16%

---

# 步驟事件欄位清單 {#sharing-field-list}

步驟事件欄位按類別組織。

* 調試資訊欄位
* 歷程欄位
* 配置檔案欄位
* 服務事件欄位

## 調試資訊

| 欄位名稱 | 類型 | 說明 |
|---|---|------------|
| 請求ID | 字串 | Journey Orchestration用於跟蹤請求流的請求ID。 |

## 旅程

此欄位組用於行程架構（與journeyStepEvent相關）。 它包含以下欄位：

| 欄位名稱 | 類型 | 說明 |
|---|---|------------|
| ID | 字串 | 給定行程的標識符 |
| 版本ID | 字串 | 行程版本的ID。 此ID表示旅程的標識 |
| 名稱 | 字串 | 行程名稱 |
| 描述 | 字串 | 行程描述 |
| 版本 | 字串 | 版本，表示為 `major`。`minor` |

## 輪廓

此欄位組特定於journeyStepEvent:此事件與journey相關，並且沒有identityMap，無法描述配置檔案標識（如果有）。

對於journeyStepEvent，我們還需要添加與標識相關的欄位：

| 欄位名稱 | 類型 | 說明 |
|---|---|------------|
| ID | 字串 | 配置檔案標識符標識在行程中發送/使用的配置檔案。 例如：foo@adobe.com。 |
| namespace | 字串 | 此欄位描述「行程」中使用的配置檔案引用的命名空間。 例如：電子郵件， ECID |

## 服務事件

此混合包含與配置檔案導出作業對應的所有欄位。

| 欄位名稱 | 類型 | 說明 |
|---|---|------------|
| ID | 字串 | 觸發的段導出作業的標識符 |
| 狀態 | 字串 | 段導出作業的狀態：排隊，已開始，已完成 |
| 導出計數總計 | 整數 | 段導出作業的最大可能值 |
| exportCountRecived | 整數 | 通過作業導出的段的實際數 |
| exportCountFailed | 整數 | 通過作業導出時失敗的段數 |
| 導出段ID | 字串 | 要導出的段的標識符 |
| 事件類型 | 字串 | 指示它是否是資訊事件的錯誤事件的事件類型：資訊，錯誤 |
| 事件代碼 | 字串 | 指示相應eventType原因的錯誤代碼 |

## 步驟事件

此類別包含原始步驟事件欄位。 請參閱此 [節](../building-journeys/sharing-legacy-fields.md)。
