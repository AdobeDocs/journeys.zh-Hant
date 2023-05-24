---
product: adobe campaign
title: 日誌步驟事件常用欄位
description: 日誌步驟事件常用欄位
feature: Journeys
role: User
level: Intermediate
exl-id: 5cf8e6b5-2162-4aa3-b071-96ede31948e6
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 9%

---

# 日誌步驟事件常用欄位 {#sharing-common-fields}

此混合將由journeyStepEvent和journeyStepProfileEvent共用。

這些是常見的XDM欄位 [!DNL Journey Orchestration] 寄給Adobe Experience Platform。 將為在行程中處理的每個步驟發送公用欄位。 更具體的欄位用於自定義操作和加密。

某些欄位僅在特定處理模式（操作執行、資料提取等）中可用 以限制事件的大小。

## 入口

指示用戶是否已輸入行程。 如果不存在，則假定值為false。

類型: 布林值

值：真假

## 重新入口

指示用戶是否使用同一實例重新輸入行程。 如果不存在，則假定值為false。

類型: 布林值

值：真假

## 實例結束

指示實例是否已結束（成功或未成功）。

類型: 布林值

## 事件ID

處理中的事件ID，用於步驟處理。 如果事件是外部事件，則值為其eventId。 如果事件是內部事件，則值為內部事件ID（如scheduledNotificationReceived、executedAction等）。

類型: 字串

## 節點ID

客戶端節點ID（從畫布）。

類型: 字串

## 步驟ID

當前正在處理的步驟的唯一ID。

類型: 字串

## 步驟名稱

當前正在處理的步驟的名稱。

類型: 字串

## 步驟類型

步驟的類型。

類型: 字串

可能的值：

* 條件
* 動作
* 排程器
* 計時器

## 步驟狀態

完成步驟處理（以及觸發步驟事件）時步驟的狀態，表示步驟的狀態。

類型: 字串

該狀態有可能是：

* 結束：該步驟沒有轉換，其處理已成功結束。
* 錯誤：步驟處理引發錯誤。
* 過渡：該步驟正在等待事件轉換到另一個步驟。
* 封閉：該步驟在操作或富集期間引發的封蓋錯誤上失敗。
* timedout:步驟在超時錯誤時失敗，在操作或富集期間引發。
* 實例時間：該步驟已停止其處理，因為實例已達到其超時。

## 旅程ID

旅程的ID。

類型: 字串

## journeyVersionID

行程版本的ID。 此ID表示對journey的標識引用（對於journeyStepEvent）。

類型: 字串

## journey版本名

行程版本的名稱。

類型: 字串

## journey版本

行程版本。

類型: 字串

## 實例ID

行程實例的內部ID。

類型: 字串

## 外部密鑰

從事件中提取外部密鑰以處理它。

類型: 字串

## 父步驟ID

實例中當前已處理步驟的父代的步驟ID。

類型: 字串

## 父步驟名稱

當前步驟的父代的步驟名稱。

類型: 字串

## parentTransitionID

將實例帶到已處理步驟的轉換的ID。

類型: 字串

## 父級轉換名

將實例帶到已處理步驟的轉換的名稱。

類型: 字串

## 在測試中

指示此行程是否處於test模式。

類型: 布林值

## 處理時間

從實例步驟入口到處理結束的總時間（毫秒）。

類型：長

## 實例類型

指示實例類型（如果為批或酉）。

類型: 字串

值：批/單

## 定期索引

如果行程是批處理且是循環的，則重複的索引（第一次運行的recurrenceIndex = 1）。

類型：長

## 是BatchToUnigary

指示是否已從批實例觸發此單一實例。

類型: 布林值

## batchExternalKey

批處理事件的外部密鑰。

類型: 字串

## batchInstanceID

這是批實例ID。

類型: 字串

## batchUnimaryBranchID

如果實例是從批處理實例（酉分支ID）觸發的。

類型: 字串
