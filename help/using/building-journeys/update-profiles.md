---
product: adobe campaign
solution: Journey Orchestration
title: 從一個歷程跳到另一個歷程
description: 從一個歷程跳到另一個歷程
feature: 旅程
role: 業務從業人員
level: 中級
translation-type: tm+mt
source-git-commit: 8685dfdcbfb414af89b304a6a9a0f9418959909b
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 3%

---


# 更新配置檔案{#update-profile}

**[!UICONTROL Update profile]**&#x200B;動作活動可讓您更新現有的Adobe Experience Platform描述檔，其中包含來自事件、資料來源或使用特定值的資訊。

## 重要附註

* **更新描述檔**&#x200B;動作只能用於從具有命名空間的事件開始的歷程記錄。
* 動作只會更新現有欄位，不會建立新的描述檔欄位。
* 您無法使用&#x200B;**更新描述檔**&#x200B;動作來產生體驗事件，例如購買。
* 如同其他任何動作，您可以在發生錯誤或逾時時時定義替代路徑，且無法並行放置兩個動作。
* 傳送至平台的更新要求會很快，但不會立即／在一秒內。 通常需要幾秒鐘，但有時需要更多時間，但無法保證。 因此，例如，如果動作使用「欄位1」，而「更新描述檔」動作則會以前定位，因此您不應預期「欄位1」會在動作中更新。
* 資料來源在欄位群組層級有快取持續時間的概念。 如果您預期在歷程中會利用最近更新的描述檔欄位，請務必定義非常短的快取持續時間。

## 使用測試模式{#using-the-test-mode}

在測試模式中，不會模擬描述檔更新。 更新將在測試描述檔上執行。

只有測試描述檔可以在測試模式中進入歷程。 您可以建立新的測試描述檔，或將現有的描述檔轉換為測試描述檔。 在Adobe Experience Platform中，您可以透過API呼叫更新描述檔屬性，但無法透過介面執行。 最簡單的方式是使用&#x200B;**更新描述檔**&#x200B;動作活動，並將測試描述檔布林欄位從false變更為true。

有關測試模式的詳細資訊，請參閱此[部分](../building-journeys/testing-the-journey.md)。

## 使用描述檔更新

1. 從活動開始設計您的旅程。 請參閱此[節](../building-journeys/journey.md)。

1. 在浮動視窗的&#x200B;**Action**&#x200B;區段中，將&#x200B;**Update profile**&#x200B;活動拖曳至畫布中。

   ![](../assets/profileupdate0.png)

1. 從清單中選擇方案。

1. 按一下&#x200B;**欄位**&#x200B;以選擇要更新的欄位。 只能選取一個欄位。

   ![](../assets/profileupdate2.png)

1. 從清單中選取資料集。 資料集選擇將決定描述檔欄位的新值儲存位置。

1. 按一下&#x200B;**Value**&#x200B;欄位，以定義您要使用的值：

   * 使用簡單運算式編輯器，您可以從資料來源或傳入事件中選取欄位。

      ![](../assets/profileupdate4.png)

   * 如果要定義特定值或利用高級函式，請按一下&#x200B;**高級模式**。

      ![](../assets/profileupdate3.png)

**更新描述檔**&#x200B;現在已設定。

![](../assets/profileupdate1.png)
