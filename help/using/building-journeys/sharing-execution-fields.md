---
title: journeyStep事件動作執行欄位
description: journeyStep事件動作執行欄位
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
source-git-commit: 10402a774bda66629f30869102d5e6ceca267535
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 0%

---


# journeyStep事件動作執行欄位 {#sharing-execution-fields}

此混搭將由journeyStepEvent和journeyStepProfileEvent分享。

如果步驟有動作要處理，這些欄位將新增至事件裝載。

## actionID

正在執行之動作的ID。

類型： 字串

## actionName

動作的名稱。 如果尚未設定任何名稱，則會採用stepName。

類型： 字串

## actionType

動作的類型。

類型： 字串

## actionParametred

指出動作是否為參數化。

類型： 布林值

## actionExecutionTime

執行當前操作所花費的時間（以毫秒為單位）。

類型： long

## actionExecutionError

呼叫動作時發生的錯誤類型。

類型： 字串

值：
* http
* 覆蓋
* 超時
* 錯誤

## actionExecutionErrorCode

動作執行錯誤的程式碼。 如果錯誤有程式碼（例如HTTP程式碼），則呈現。

類型： 字串

## actionExecutionOriginError

逾時可能發生兩種情況：

* 第一次嘗試時，會執行動作。 在這種情況下，執行尚未完成，因此沒有基本錯誤
* 重試時： 在這種情況下，actionExecOrigError/actionExecOrigErrorCode描述重試前在嘗試時遇到的錯誤。

例如，正在傳送電子郵件，並在第一次嘗試時傳回HTTP 500錯誤。 會重試讀取，但2次嘗試的持續時間超過逾時。 然後，動作執行會標籤為逾時。 動作部分會如下所示：

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

類型： 字串

## actionExecutionOriginCode

actionExecOrigError的錯誤代碼。

類型： 字串

## actionBusinessType

指示動作類型。

值：

* 建築物
* ACS電子郵件
* ACS SMS
* ACS推送
* 客戶
* ε
* ...

類型： 字串

## deliveryJobID

此說明批次歷程的傳送工作ID。

類型： 字串

## batchDeliveryID

此說明批次歷程的傳送ID。

類型： 字串

## fromSegmentTrigger

此說明是否從「對象區段」觸發「批次歷程」。

類型： 布林值

## actionSchedulerCount

在步驟處理期間發送到調度器服務的調度器通知請求計數。

類型： long
