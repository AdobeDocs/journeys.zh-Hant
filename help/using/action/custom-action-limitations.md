---
title: 自訂動作限制
description: 瞭解自訂動作限制
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# 自訂動作限制 {#concept_lh2_df1_2gb}

以下是使用自訂動作的一些限制：

* 沒有封頂或傳送卷緩衝／平滑。
* 系統地在發生錯誤時執行兩次重試。 您無法根據收到的錯誤訊息調整重試次數。
* 內建事 **[!UICONTROL Reaction]**件可讓您對現成可用的動作做出反應(請參閱[](../building-journeys/event-activities.md)。 如果您想要回應透過自訂動作傳送的訊息，則必須設定專屬事件。
* 自訂動作URL不支援動態參數。
* 僅支援POST和PUT呼叫方法。
* 查詢參數或標題的名稱不能以&quot;。&quot;開頭。 或「$」。
* 不允許IP位址。
* 內部Adobe位址(.adobe.)不允許。
