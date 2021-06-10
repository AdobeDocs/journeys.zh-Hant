---
product: adobe campaign
title: 從一個歷程跳到另一個歷程
description: 從一個歷程跳到另一個歷程
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: eaf2c795-0920-4b9c-9f06-801e43c1844b
source-git-commit: 29aa6b6e16f8e6d051065f8157f4e25e8b1c05e1
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 4%

---

# 更新設定檔 {#update-profile}

**[!UICONTROL Update profile]**&#x200B;動作活動可讓您使用來自事件、資料來源或使用特定值的資訊更新現有的Adobe Experience Platform設定檔。

## 重要附註

* **更新設定檔**&#x200B;動作只能用於從具有命名空間的事件開始的歷程中。
* 動作只會更新現有欄位，不會建立新的設定檔欄位。
* 您無法使用&#x200B;**更新設定檔**&#x200B;動作來產生體驗事件，例如購買。
* 如同任何其他動作，您可以在發生錯誤或逾時的情況下定義替代路徑，且無法同時放置兩個動作。
* 傳送至Platform的更新請求會很快，但不會立即/在一秒內傳送。 通常需要幾秒鐘時間，但有時更多時間卻無法保證。 因此，例如，如果動作使用「欄位1」，而此欄位是由位於之前的「更新設定檔」動作更新，則您不應期望動作中的「欄位1」會更新。
* 資料來源在欄位群組層級有快取持續時間的概念。 如果您預期會在歷程中運用最近更新的設定檔欄位，請務必定義非常短的快取期間。
* 在測試模式中，將不會模擬設定檔更新。 將對測試設定檔執行更新。

## 使用設定檔更新

1. 從事件開始，設計您的歷程。 請參閱此[節](../building-journeys/journey.md)。

1. 在浮動視窗的&#x200B;**Action**&#x200B;區段中，將&#x200B;**Update profile**&#x200B;活動拖曳至畫布中。

   ![](../assets/profileupdate0.png)

1. 從清單中選擇架構。

1. 按一下&#x200B;**欄位**&#x200B;以選擇要更新的欄位。 只能選取一個欄位。

   ![](../assets/profileupdate2.png)

1. 從清單中選取資料集。

   >[!NOTE]
   >
   >**更新設定檔**&#x200B;動作會即時更新設定檔資料，但不會更新資料集。 設定檔是與資料集相關的記錄，因此需要選取資料集。

1. 按一下&#x200B;**值**&#x200B;欄位以定義您要使用的值：

   * 使用簡單運算式編輯器，您可以從資料來源或傳入事件中選取欄位。

      ![](../assets/profileupdate4.png)

   * 如果要定義特定值或利用高級函式，請按一下&#x200B;**高級模式**。

      ![](../assets/profileupdate3.png)

**更新設定檔**&#x200B;現已設定完畢。

![](../assets/profileupdate1.png)
