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
source-git-commit: f4f41428b19f611da15b20a1788b240fadfd49fa

---



# 時區管理 {#timezone_management}

您可以在歷程的屬性中 [定義](../building-journeys/changing-properties.md) 時區。

若要存取「屬性」，請按一下螢幕右上角的鉛筆圖示。

此時區將用於歷程中包含時間元素(例如：

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

您可以選擇時區，或選擇使用用戶配置檔案中定義的時區。

## 定義固定時區 {#fixed-timezone}

時區也可以固定。 清除預先定義的時區，並從下拉式清單中選擇一個時區。 如果您使用固定的時區，則所有進入旅程的個人都會使用相同的時區。

要執行此操作，請在 **[!UICONTROL Properties]**&#x200B;中選擇時區。

![](../assets/journey73.png)

## 使用描述檔來定義旅程時區 {#timezone-from-profiles}

如果旅程的登入事件具有命名空間，表示旅程可以到達資料平台的即時客戶個人檔案服務，則時區會預先定義為在旅程中流入的個人個人檔案中指定的時區。

如果在Experience platform設定檔中定義時區，則可在歷程中擷取時區。

如果個人的描述檔不包含時區，則擷取的時區將是時區欄位中定義的時區。

若要這麼做，請 **[!UICONTROL Properties]**&#x200B;先檢查 **[!UICONTROL Use Profile timezone in timers and conditions]**。

![](../assets/journey72.png)

## 在運算式中使用時區 {#timezone-in-expressions}

時區是用進階運算式編輯器來建立運算式。 在這種情況下，將使用表達式編輯器來選擇希望系統獲取此資訊的位置。 參見[](../expression/expressionadvanced.md)。

旅程的開始和結束日期無法連結至特定時區。 它們會自動關聯至例項的時區。
