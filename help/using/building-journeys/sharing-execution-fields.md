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

如果步驟有要處理的操作，則這些欄位將添加到事件負載。

## 操作ID

正在執行的操作的ID。

類型: 字串

## 操作名稱

操作的名稱。 如果未設定名稱，則將採用stepName。

類型: 字串

## 操作類型

操作的類型。

類型: 字串

## actionParameted

指示操作是否參數化。

類型: 布林值

## actionExecutionTime

執行當前操作所用的時間（毫秒）。

類型：長

## actionExecutionError

調用操作時發生的錯誤類型。

類型: 字串

值：
* http
* 封蓋
* timeout
* error

## actionExecutionErrorCode

操作執行錯誤的代碼。 如果錯誤有代碼（如HTTP代碼），則顯示。

類型: 字串

## actionExecutionOriginError

在以下兩種情況下，可能會出現超時：

* 第一次嘗試時，執行操作。 在這種情況下，執行未完成，因此不存在基本錯誤
* 重試：在這種情況下，actionExecOrigError/actionExecOrigErrorCode描述重試前在嘗試時遇到的錯誤。

例如，正在發送電子郵件，在第一次嘗試時會返回HTTP 500錯誤。 重試讀取，但兩次嘗試的持續時間超過超時。 然後，將操作執行標籤為超時。 操作部分將如下所示：

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

指示操作類型。

值：

* 建築物
* ACS電子郵件
* ACS簡訊
* ACS推送
* 客戶
* ε
* ...

類型: 字串

## deliveryJobID

這描述批行程的交貨作業ID。

類型: 字串

## batchDeliveryID

這描述批行程的交貨ID。

類型: 字串

## fromSegmentTrigger

此說明是否從受眾段觸發批行程。

類型: 布林值

## actionSchedulerCount

在步驟處理期間發送到調度程式服務的調度程式通知請求計數。

類型：長
