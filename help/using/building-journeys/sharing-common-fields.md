---
title: journeysteps事件常用欄位
description: journeysteps事件常用欄位
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
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---


# journeysteps事件常用欄位 {#sharing-common-fields}

此混搭將由journeyStepEvent和journeyStepProfileEvent分享。

這些是傳送至Adobe Data Platform [!DNL Journey Orchestration] 的常見XDM欄位。 在歷程中處理的每個步驟都會傳送常用欄位。 自訂動作和擴充會使用更多特定欄位。

其中有些欄位僅適用於特定處理模式（動作執行、資料擷取等） 以限制事件的大小。

## 入口

指出使用者是否已進入歷程。 如果不存在，我們假設該值為false。

類型： 布林值

值： true/false

## 重入

指出使用者是否已使用相同例項重新進入歷程。 如果不存在，我們假設該值為false。

類型： 布林值

值： true/false

## instanceEnded

指出例項是否已結束（成功與否）。

類型： 布林值

## eventID

處理中的事件ID，用於步驟處理。 如果事件是外部事件，則值為其eventId。 如果事件是內部事件，則值為內部eventId（例如scheduledNotificationReceived、executedAction等）。

類型： 字串

## nodeID

用戶端節點ID（來自畫布）。

類型： 字串

## stepID

目前正在處理之步驟的唯一ID。

類型： 字串

## stepName

目前正在處理的步驟名稱。

類型： 字串

## stepType

步驟的類型。

類型： 字串

可能的值：

* 條件
* 動作
* 排程器
* 計時器

## stepStatus

步驟的狀態，代表步驟的狀態，處理完成時（以及引發步驟事件）。

類型： 字串

狀態可以是：

* 結束： 此步驟沒有轉換，其處理已成功結束。
* 錯誤： 步驟處理已引發錯誤。
* 轉變： 此步驟正在等待事件轉換到另一個步驟。
* capped: 在動作或擴充期間，步驟因封閉錯誤而失敗。
* timedout: 步驟因逾時錯誤而失敗，在動作或擴充期間引發。
* instanceTimedout: 步驟已停止處理，因為實例已達到其超時。

## journeyID

旅程的ID。

類型： 字串

## journeyVersionID

歷程版本的ID。 此ID代表歷程的身分參考，若是journeyStepEvent。

類型： 字串

## journeyVersionName

歷程版本的名稱。

類型： 字串

## journeyVersion

歷程版本。

類型： 字串

## instanceID

歷程例項的內部ID。

類型： 字串

## externalKey

從事件擷取外部金鑰以處理它。

類型： 字串

## parentStepID

實例中當前處理步驟的父代的步驟ID。

類型： 字串

## parentStepName

當前步驟的父代的步驟名。

類型： 字串

## parentTransitionID

將實例帶到處理步驟的轉換的ID。

類型： 字串

## parentTransitionName

將實例帶到處理步驟的轉換的名稱。

類型： 字串

## inTest

指出此歷程是否處於測試模式。

類型： 布林值

## processingTime

從例項步驟進入到處理結束的總時間（毫秒）。

類型： long

## instanceType

指示實例類型（如果是批或單一）。

類型： 字串

值： 批處理／酉

## recurrenceIndex

如果歷程是批次且循環的，則循環的索引（第一次執行具有recurrencyIndex = 1）。

類型： long

## isBatchToUnignation

指示是否已從批實例觸發此單一實例。

類型： 布林值

## batchExternalKey

批次事件的外部索引鍵。

類型： 字串

## batchInstanceID

這是批次實例ID。

類型： 字串

## batchUnignalBranchID

如果實例是從批次實例觸發的，則為酉分支ID。

類型： 字串
