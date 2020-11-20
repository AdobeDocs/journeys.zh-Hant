---
product: adobe campaign
solution: Journey Orchestration
title: journeyStep 事件資料擷取欄位
description: journeyStep 事件資料擷取欄位
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 4%

---


# journeyStep 事件資料擷取欄位 {#sharing-fetch-fields}

此混搭將由journeyStepEvent和journeyStepProfileEvent分享。

在步驟處理期間，我們可以在欄位群組上取得N個資料。

## fetchTotalTime

在步驟處理期間，以百萬計的單位表示的資料擷取總花費時間。

類型：long

## fetchTypeInError

定義擷取錯誤是在Adobe Experience Platform上還是在自訂資料來源上。

類型：字串

值：
* aep
* 自訂

## fetchError

處理資料擷取時發生的錯誤類型。

類型：字串

值：
* http
* 覆蓋
* timedout
* 錯誤

## fetchErrorCode

擷取錯誤的程式碼。 如果錯誤有程式碼（例如HTTP程式碼），則呈現。 例如，如果actionExecError為http，代碼404代表HTTP 404錯誤。

類型：字串

## fetchOriginError

逾時可能發生兩種情況：

* 第一次嘗試時，會執行動作。 在這種情況下，執行尚未完成，因此沒有基本錯誤
* 重試時：在這種情況下，actionExecOrigError/actionExecOrigErrorCode描述重試前在嘗試時遇到的錯誤。

例如，從Unified Profile Service擷取資料，並在第一次嘗試時傳回HTTP 500錯誤。 會重試讀取，但2次嘗試的持續時間超過逾時。 然後，動作執行會標籤為逾時。 動作部分會如下所示：

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

系統提供的錯誤代碼 [!DNL Journey Orchestration] 正在查詢。 例如，它可以是404、500等。

類型：字串

## fetchCount

無論來源類型為何，資料被讀取的次數。

類型：long

## fetchPlatformTotalTime

從Adobe Experience Platform擷取資料所花費的總時間（以百萬計）。 備注：該時間量從引擎將富集事件發送到富集服務並接收響應的時間開始計算。

類型：long

## fetchPlatformCount

從Adobe Experience Platform擷取資料的次數。

類型：long

## fetchCustomTotalTime

以毫秒為單位的自訂資料擷取時間。 備注：從引擎將富集事件發送到富集服務並接收響應的時間開始計算該時間量

類型：long

## fetchCustomCount

從外部系統擷取自訂資料的次數。

類型：long
