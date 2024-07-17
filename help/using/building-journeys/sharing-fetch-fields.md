---
product: adobe campaign
title: journeyStep 事件資料擷取欄位
description: journeyStep 事件資料擷取欄位
feature: Journeys
role: User
level: Intermediate
exl-id: 4df471ae-c6b7-452e-8e44-a108d0da276f
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 4%

---

# journeyStep 事件資料擷取欄位 {#sharing-fetch-fields}

此Mixin將由journeyStepEvent和journeyStepProfileEvent共用。

在步驟處理期間，我們可以在欄位群組中擷取N筆資料。

## fetchTotalTime

在步驟處理期間，花費在資料擷取上的總時間（毫秒）。

型別： long

## fetchTypeInError

定義擷取作業錯誤是在Adobe Experience Platform上還是在自訂資料來源上。

型別：字串

值：
* aep
* 自訂

## fetchError

處理資料擷取時發生的錯誤型別。

型別：字串

值：
* http
* 上限
* 逾時
* 錯誤

## fetchErrorCode

擷取錯誤的程式碼。 如果錯誤有程式碼（例如HTTP程式碼）則會出現。 例如，如果actionExecError是http，則代碼404代表HTTP 404錯誤。

型別：字串

## fetchOriginError

在兩種情況下，可能會發生逾時：

* 在第一次嘗試時會執行動作。 在此情況下，執行未完成，因此沒有基礎錯誤
* 重試：在此情況下，actionExecOrigError/actionExecOrigErrorCode會說明在重試之前嘗試遇到的錯誤。

例如，正在從整合設定檔服務擷取資料，且第一次嘗試時會傳回HTTP 500錯誤。 會重試擷取，但嘗試2次的持續時間超過逾時。 之後，該動作執行會被標籤為逾時。 動作部分看起來會像這樣：

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

型別：字串

## fetchOriginErrorCode

系統[!DNL Journey Orchestration]提供的錯誤碼正在查詢。 例如，可以是404、500等。

型別：字串

## fetchCount

擷取資料的次數，無論來源型別為何。

型別： long

## fetchPlatformTotaltime

從Adobe Experience Platform擷取資料所需的總時間（以Millis為單位）。 備註：此時間長度是從引擎將擴充事件傳送至擴充服務並接收回應時開始計算。

型別： long

## Fetchplatformcount

從Adobe Experience Platform擷取資料的次數。

型別： long

## fetchCustomTotalTime

擷取自訂資料的時間（以毫秒為單位）。 備註：此時間量是從引擎將擴充事件傳送至擴充服務並接收回應時開始計算

型別： long

## Fetchcustomcount

從外部系統擷取自訂資料的次數。

型別： long
