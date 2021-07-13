---
product: adobe campaign
title: journeysteps事件常用欄位
description: journeysteps事件常用欄位
feature: 歷程
role: User
level: Intermediate
exl-id: 5cf8e6b5-2162-4aa3-b071-96ede31948e6
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 9%

---

# journeysteps事件常用欄位 {#sharing-common-fields}

此混合將由journeyStepEvent和journeyStepProfileEvent共用。

這些是[!DNL Journey Orchestration]傳送至Adobe Experience Platform的通用XDM欄位。 歷程中處理的每個步驟都會傳送通用欄位。 自訂動作和擴充會使用更特定的欄位。

其中有些欄位僅適用於特定處理模式（動作執行、資料擷取等） 以限制事件的大小。

## 入口

指出使用者是否已進入歷程。 若不存在，我們會假設值為false。

類型: 布林值

值：true/false

## 重新入口

指出使用者是否已使用相同例項重新進入歷程。 若不存在，我們會假設值為false。

類型: 布林值

值：true/false

## instanceEnded

指出執行個體是否已結束（成功或未成功）。

類型: 布林值

## eventID

處理中的事件ID，用於步驟處理。 如果事件為外部事件，則值為其eventId。 如果事件是內部事件，則值為內部eventId（例如scheduledNotificationReceived、executedAction等）。

類型: 字串

## nodeID

用戶端節點id（來自畫布）。

類型: 字串

## stepID

目前正在處理之步驟的唯一ID。

類型: 字串

## stepName

目前正在處理的步驟名稱。

類型: 字串

## stepType

步驟的類型。

類型: 字串

可能的值：

* 條件
* 動作
* 排程器
* 計時器

## stepStatus

完成處理時（和引發步驟事件），步驟的狀態代表步驟的狀態。

類型: 字串

狀態可以是：

* 已結束：步驟沒有轉變，其處理已成功結束。
* 錯誤：步驟處理已引發錯誤。
* 轉變：步驟正在等待事件轉變至另一個步驟。
* 上限：在動作或擴充期間引發的限定錯誤上，步驟失敗。
* 逾時：在動作或擴充期間引發的逾時錯誤上，步驟已失敗。
* instanceTimedout:步驟已停止其處理，因為例項已達逾時。

## journeyID

歷程ID。

類型: 字串

## journeyVersionID

歷程版本ID。 此id代表歷程的身分參考，若為journeyStepEvent。

類型: 字串

## journeyVersionName

歷程版本名稱。

類型: 字串

## journeyVersion

歷程版本。

類型: 字串

## instanceID

歷程例項的內部ID。

類型: 字串

## externalKey

從事件擷取的外部金鑰加以處理。

類型: 字串

## parentStepID

執行個體中目前已處理步驟的父項的步驟ID。

類型: 字串

## parentStepName

當前步驟的父級的步驟名。

類型: 字串

## parentTransitionID

將執行個體帶至已處理步驟的轉變ID。

類型: 字串

## parentTransitionName

將執行個體帶至已處理步驟的轉變名稱。

類型: 字串

## inTest

指出此歷程是否處於測試模式。

類型: 布林值

## processingTime

從執行個體步驟入口到處理結束的總時間量（毫秒）。

類型：long

## instanceType

指示實例類型（如果為批或單一）。

類型: 字串

值：批次/單一

## recurrenceIndex

如果歷程為批次和循環，則循環的索引（首次執行的recurrenceIndex = 1）。

類型：long

## isBatchToUnimation

指出此單一例項是否已從批次例項觸發。

類型: 布林值

## batchExternalKey

批次事件的外部索引鍵。

類型: 字串

## batchInstanceID

這是批次執行個體ID。

類型: 字串

## batchUnigalBranchID

如果例項是從批次例項觸發，則為單一分支ID。

類型: 字串
