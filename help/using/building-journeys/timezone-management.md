---
product: adobe campaign
title: 時區管理
description: 瞭解時區管理
feature: Journeys
role: User
level: Intermediate
exl-id: c0e67849-caa0-4045-94ed-38e483054e1d
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 8%

---

# 時區管理 {#timezone_management}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_



您可以在歷程的[屬性](../building-journeys/changing-properties.md)中定義時區。

若要存取「屬性」，請按一下畫面右上方的鉛筆圖示。

此時區將用於包含時間元素的歷程的每個活動，例如：

* [時間條件](../building-journeys/condition-activity.md#time_condition)
* [日期條件](../building-journeys/condition-activity.md#date_condition)
* [自訂等待](../building-journeys/wait-activity.md#custom)

您可以選取時區，或選擇使用使用者設定檔中定義的時區。

>[!NOTE]
>
>設定檔時區與&#x200B;**偏好設定詳細資料**&#x200B;欄位群組中現有的&#x200B;**時區**&#x200B;欄位搭配使用。

## 定義固定時區 {#fixed-timezone}

時區也可以固定。 清除預先定義的時區，並從下拉式清單中選取一個時區。 如果您使用固定時區，則所有進入歷程的個人都將使用相同的時區。

若要這麼做，請在&#x200B;**[!UICONTROL Properties]**&#x200B;中選取時區。

![](../assets/journey72.png)

## 使用設定檔來定義歷程時區 {#timezone-from-profiles}

如果歷程的進入事件具有名稱空間，這表示歷程可以存取Adobe Experience Platform的即時客戶設定檔服務，您可能會想要使用設定檔層級定義的時區。 若要這麼做，請在&#x200B;**屬性**&#x200B;中勾選&#x200B;**在等待和條件中使用設定檔時區**。 預設不會勾選此選項。

如果已為輪廓定義了時區，則歷程將擷取並使用該時區。如果沒有，則使用的時區將是時區欄位中定義的時區。

![](../assets/journey73.png)

## 在運算式中使用時區 {#timezone-in-expressions}

歷程的開始和結束日期無法連結至特定時區。 它們會自動關聯至執行個體的時區。
