---
title: 步驟事件欄位清單
description: 步驟事件欄位清單
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 177b4a97-c757-40ca-a190-fbd88169e5e2
source-git-commit: 4291dfc91c2fb29d294416ceed022ee00842c870
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 12%

---

# 步驟事件欄位清單 {#sharing-field-list}

步驟事件欄位會依類別組織。

* 除錯資訊欄位
* 歷程欄位
* 設定檔欄位
* 服務事件欄位

## debugInfo

| 欄位名稱 | 類型 | 說明 |
|---|---|------------|
| requestId | 字串 | Journey Orchestration用來追蹤請求流程的請求ID。 |

## 歷程

此欄位群組用於歷程結構（與journeyStepEvent相關）。 它包含下列欄位：

| 欄位名稱 | 類型 | 說明 |
|---|---|------------|
| ID | 字串 | 指定歷程的識別碼 |
| VersionID | 字串 | 歷程版本ID。 此id代表歷程的身分 |
| 名稱 | 字串 | 歷程名稱 |
| 說明 | 字串 | 歷程說明 |
| 版本 | 字串 | 版本，表示為 `major`.`minor` |

## 設定檔

此欄位群組是journeyStepEvent專屬的：此事件與歷程相關，沒有identityMap，用於說明設定檔身分（如果有）。

對於journeyStepEvent，我們也需要新增與身分相關的欄位：

| 欄位名稱 | 類型 | 說明 |
|---|---|------------|
| ID | 字串 | 設定檔識別碼可識別歷程中傳送/使用的設定檔。 例如：foo@adobe.com。 |
| namespace | 字串 | 此欄位說明歷程中使用之設定檔參考的命名空間。 例如：電子郵件、ECID |

## serviceEvents

此混合包含與設定檔匯出工作對應的所有欄位。

| 欄位名稱 | 類型 | 說明 |
|---|---|------------|
| ID | 字串 | 觸發的區段匯出作業識別碼 |
| 狀態 | 字串 | 區段匯出作業的狀態：已排隊，已開始，已完成 |
| exportCountTotal | 整數 | 區段匯出作業的最大可能值 |
| exportCountRemated | 整數 | 通過作業導出的實際段數 |
| exportCountFailed | 整數 | 通過作業導出時段數失敗 |
| exportSegmentID | 字串 | 要匯出的區段識別碼 |
| eventType | 字串 | 指示它是否為資訊事件的錯誤事件的事件類型：資訊，錯誤 |
| eventCode | 字串 | 指示相應eventType原因的錯誤代碼 |

## stepEvents

此類別包含原始步驟事件欄位。 請參閱 [節](../building-journeys/sharing-legacy-fields.md).
