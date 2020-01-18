---
title: 時區管理
description: 瞭解時區管理
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
source-git-commit: f57cc43d8f2a223c04cc4ccccb3b3c3e0bcadfc1

---



# 時區管理 {#timezone_management}

時區定義可用於以下活動：

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

如果旅程的登入事件具有命名空間，表示旅程可以到達資料平台的即時客戶個人檔案服務，則時區會預先定義為在旅程中流入的個人個人檔案中指定的時區。 如果個人的描述檔不包含時區，則會使用例項的時區。 您可以聯絡您的管理員以瞭解例項時區。

![](../assets/journey73.png)

時區也可以固定。 清除預先定義的時區，並從下拉式清單中選擇一個時區。 如果您使用固定的時區，則所有進入旅程的個人都會使用相同的時區。

![](../assets/journey72.png)

最後，每個進入步驟的人員，都可以動態顯示時區。 在這種情況下，您將使用表達式編輯器選擇希望系統獲取此資訊（可以來自事件或資料源）的位置。 參見[](../expression/expressionadvanced.md)。


旅程的開始和結束日期無法連結至特定時區。 它們會自動關聯至例項的時區。
