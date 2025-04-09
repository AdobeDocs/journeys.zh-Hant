---
product: adobe campaign
title: 更新輪廓
description: 更新輪廓
feature: Journeys
role: User
level: Intermediate
exl-id: eaf2c795-0920-4b9c-9f06-801e43c1844b
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 3%

---

# 更新輪廓 {#update-profile}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_


**[!UICONTROL Update profile]**&#x200B;動作活動可讓您使用來自事件、資料來源的資訊或使用特定值，更新現有的Adobe Experience Platform設定檔。

## 重要備註

* **更新設定檔**&#x200B;動作只能用於以具有名稱空間之事件開始的歷程。
* 該動作只會更新現有欄位，不會建立新的設定檔欄位。
* 您無法使用&#x200B;**更新設定檔**&#x200B;動作來產生體驗事件，例如購買。
* 如同任何其他動作，您可以定義發生錯誤或逾時時的替代路徑，而且您無法同時放置兩個動作。
* 傳送至Platform的更新要求會很快，但不會立即/在一秒內。 這通常需要幾秒鐘的時間，但有時更長，無法保證。 因此，舉例來說，如果動作使用「欄位1」，而此欄位是由之前放置的「更新設定檔」動作所更新，您就不應該預期動作會更新「欄位1」。
* 在測試模式中，將不會模擬設定檔更新。 更新將在測試設定檔上執行。
* **更新設定檔**&#x200B;活動不支援定義為列舉的XDM欄位。

## 使用設定檔更新

1. 從事件開始設計您的歷程。 請參閱[本章節](../building-journeys/journey.md)。

1. 在調色盤的&#x200B;**動作**&#x200B;區段中，將&#x200B;**更新設定檔**&#x200B;活動拖放到畫布中。

   ![](../assets/profileupdate0.png)

1. 從清單中選取結構描述。

1. 按一下&#x200B;**欄位**&#x200B;以選取要更新的欄位。 只能選取一個欄位。

   ![](../assets/profileupdate2.png)

1. 從清單中選取資料集。

   >[!NOTE]
   >
   >**更新設定檔**&#x200B;動作會即時更新設定檔資料，但不會更新資料集。 需要選取資料集，因為設定檔是和資料集相關的記錄。

1. 按一下&#x200B;**值**&#x200B;欄位以定義您要使用的值：

   * 使用簡單運算式編輯器，您可以從資料來源或傳入事件中選取欄位。

     ![](../assets/profileupdate4.png)

   * 若要定義特定值或運用進階函式，請按一下&#x200B;**進階模式**。

     ![](../assets/profileupdate3.png)

**更新設定檔**&#x200B;現已設定完成。

![](../assets/profileupdate1.png)
