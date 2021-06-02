---
product: adobe campaign
title: journeyStep 事件資料擷取欄位
description: journeyStep 事件資料擷取欄位
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 4df471ae-c6b7-452e-8e44-a108d0da276f
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 4%

---

# journeyStep 事件資料擷取欄位 {#sharing-fetch-fields}

此混合將由journeyStepEvent和journeyStepProfileEvent共用。

在步驟處理期間，我們可以在欄位群組上擷取N個資料。

## fetchTotalTime

步驟處理期間以毫秒為單位的資料擷取總逗留時間。

類型：long

## fetchTypeInError

定義錯誤擷取是在Adobe Experience Platform上還是在自訂資料來源上。

類型：字串

值：
* aep
* 自訂

## fetchError

處理資料擷取時發生的錯誤類型。

類型：字串

值：
* http
* 上限
* timedout
* 錯誤

## fetchErrorCode

擷取錯誤的程式碼。 如果錯誤有程式碼（例如HTTP程式碼），則顯示。 例如，如果actionExecError為http，則代碼404代表HTTP 404錯誤。

類型：字串

## fetchOriginError

逾時可能發生，有兩種情況：

* 第一次嘗試時，會執行動作。 在此情況下，執行尚未完成，因此沒有基本錯誤
* 重試時：在這種情況下，actionExecOrigError/actionExecOrigErrorCode描述重試前在嘗試時遇到的錯誤。

例如，從統一設定檔服務擷取資料，並在第一次嘗試時傳回HTTP 500錯誤。 會重試擷取，但兩次嘗試的持續時間超過逾時。 然後，動作執行會標籤為逾時。 動作部分看起來會像這樣：

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

類型：字串

## fetchOriginErrorCode

系統[!DNL Journey Orchestration]提供的錯誤代碼正在查詢。 例如，可以是404、500等。

類型：字串

## fetchCount

擷取資料的次數，無論來源類型為何。

類型：long

## fetchPlatformTotalTime

從以毫秒為單位的Adobe Experience Platform擷取資料所花的總時間。 備注：從引擎將擴充事件發送到擴充服務並接收響應的時間開始計算該時間量。

類型：long

## fetchPlatformCount

從Adobe Experience Platform擷取資料的次數。

類型：long

## fetchCustomTotalTime

以毫秒為單位擷取自訂資料的時間量。 備注：從引擎將擴充事件發送到擴充服務並接收響應的時間開始計算該時間量

類型：long

## fetchCustomCount

從外部系統擷取自訂資料的次數。

類型：long
