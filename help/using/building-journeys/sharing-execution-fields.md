---
product: adobe campaign
title: journeyStep 事件動作執行欄位
description: journeyStep 事件動作執行欄位
feature: Journeys
role: User
level: Intermediate
exl-id: 9af66037-63d7-41a8-86d1-b03c655dfb82
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 12%

---

# journeyStep 事件動作執行欄位 {#sharing-execution-fields}

此混合將由journeyStepEvent和journeyStepProfileEvent共用。

如果步驟有要處理的動作，則這些欄位將會新增至事件裝載。

## actionID

正在執行的動作ID。

類型: 字串

## actionName

動作名稱。 如果未設定名稱，則會採用stepName。

類型: 字串

## actionType

動作的類型。

類型: 字串

## actionParametered

指示操作是否為參數化。

類型: 布林值

## actionExecutionTime

執行目前動作所花費的時間（以毫秒為單位）。

類型：long

## actionExecutionError

呼叫動作時發生的錯誤類型。

類型: 字串

值：
* http
* 上限
* timeout
* error

## actionExecutionErrorCode

動作執行錯誤的程式碼。 如果錯誤有程式碼（例如HTTP程式碼），則顯示。

類型: 字串

## actionExecutionOriginError

逾時可能發生，有兩種情況：

* 第一次嘗試時，會執行動作。 在此情況下，執行尚未完成，因此沒有基本錯誤
* 重試時：在這種情況下，actionExecOrigError/actionExecOrigErrorCode描述重試前在嘗試時遇到的錯誤。

例如，會傳送電子郵件，並在第一次嘗試時傳回HTTP 500錯誤。 會重試擷取，但兩次嘗試的持續時間超過逾時。 然後，動作執行會標籤為逾時。 動作部分看起來會像這樣：

```
    ...
    "actionId": "myActionId",
    "actionName": "My mail sending",
    "actionType": "acsRestAction",
    "actionParameterized": true,
    "actionExecError": "timedout",
    "actionExecOrigError": "http",
    "actionExecOrigErrorCode": "500"
```

類型: 字串

## actionExecutionOriginCode

actionExecOrigError的錯誤代碼。

類型: 字串

## actionBusinessType

指出動作的類型。

值：

* 建置
* ACS電子郵件
* ACS簡訊
* ACS推送
* 客戶
* Epsilon
* ...

類型: 字串

## deliveryJobID

這說明批次歷程的傳送作業ID。

類型: 字串

## batchDeliveryID

這說明批次歷程的傳送ID。

類型: 字串

## fromSegmentTrigger

此說明批次歷程是否從受眾區段觸發。

類型: 布林值

## actionSchedulerCount

在步驟處理期間發送到調度程式服務的調度程式通知請求的計數。

類型：long
