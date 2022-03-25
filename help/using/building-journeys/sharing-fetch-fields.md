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
source-wordcount: '371'
ht-degree: 7%

---

# journeyStep 事件資料擷取欄位 {#sharing-fetch-fields}

此混合將由journeyStepEvent和journeyStepProfileEvent共用。

在步驟處理過程中，可以對欄位組進行N個資料提取。

## 提取總時間

在步驟處理期間以毫秒為單位的資料讀取所花費的總時間。

類型：長

## fetchTypeInError

定義讀取錯誤是在Adobe Experience Platform上還是在自定義資料源上。

類型: 字串

值：
* 阿普
* 自定義

## fetchError

處理資料提取時發生的錯誤類型。

類型: 字串

值：
* http
* 封蓋
* 滴
* error

## fetchErrorCode

讀取錯誤的代碼。 如果錯誤有代碼（如HTTP代碼），則顯示。 例如，如果actionExecError為http，則代碼404表示HTTP 404錯誤。

類型: 字串

## fetchOriginError

在以下兩種情況下，可能會出現超時：

* 第一次嘗試時，執行該操作。 在這種情況下，執行未完成，因此不存在基本錯誤
* 重試：在這種情況下，actionExecOrigError/actionExecOrigErrorCode描述重試前在嘗試時遇到的錯誤。

例如，正在從Unified Profile Service中讀取資料，在第一次嘗試時返回HTTP 500錯誤。 重試讀取，但兩次嘗試的持續時間超過超時。 然後，將操作執行標籤為超時。 操作部分將如下所示：

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

類型: 字串

## fetchOriginErrorCode

系統提供的錯誤代碼 [!DNL Journey Orchestration] 正在查詢。 例如，它可以是404、500等。

類型: 字串

## 提取計數

讀取資料的次數，與源類型無關。

類型：長

## fetchPlatformTotalTime

從以百萬為單位的Adobe Experience Platform獲取資料所花費的總時間。 備注：該時間量從引擎將富集事件發送到富集服務並接收響應的時間計算。

類型：長

## fetchPlatformCount

從Adobe Experience Platform獲取資料的次數。

類型：長

## fetchCustomTotalTime

以毫秒為單位提取自定義資料的時間。 備注：從引擎將富集事件發送到富集服務並接收響應的時間計算該時間量

類型：長

## fetchCustomCount

從外部系統獲取自定義資料的次數。

類型：長
