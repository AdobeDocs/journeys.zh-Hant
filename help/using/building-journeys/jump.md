---
product: adobe campaign
title: 從一個歷程跳到另一個歷程
description: 從一個歷程跳到另一個歷程
feature: Journeys
role: User
level: Intermediate
exl-id: 520376aa-2cb5-46d6-8f21-3e03544f5da1
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 6%

---

# 從一個歷程跳到另一個歷程 {#jump}

此 **[!UICONTROL Jump]** 動作活動可讓您將個人從一個歷程推送到另一個歷程。 此功能可讓您：

* 將複雜歷程分割為數個歷程，以簡化極為複雜的設計
* 根據常見且可重複使用的歷程模式來建立歷程

在來源歷程中，只需新增 **[!UICONTROL Jump]** 活動並選取目標歷程。 當個人進入 **[!UICONTROL Jump]** 步驟，內部事件會傳送至目標歷程的第一個事件。 如果 **[!UICONTROL Jump]** 動作成功，個人將繼續在歷程中前進。 此行為與其他動作類似。

在目標歷程中，由內部觸發的第一個事件 **[!UICONTROL Jump]** 活動會使歷程中的個別流程運作。

>[!NOTE]
>
>另請參閱教學課程影片 [此處](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html?lang=zh-Hant)

## 生命週期

假設您已新增 **[!UICONTROL Jump]** 歷程A到歷程B中的活動。歷程A是 **來源歷程** 和歷程B， **目標歷程**.
以下是執行程式的不同步驟：

**歷程A** 從外部事件觸發：

1. 歷程A會接收與個人相關的外部事件。
1. 個人到達 **[!UICONTROL Jump]** 步驟。
1. 個人會推送至歷程B，並在後續步驟中前往歷程A **[!UICONTROL Jump]** 步驟。

在歷程B中，第一個事件會透過在內部觸發。 **[!UICONTROL Jump]** 來自歷程A的活動：

1. 歷程B從歷程A收到內部事件。
1. 個人開始在「歷程B」中流動。

>[!NOTE]
>
>歷程B也可以透過外部事件觸發。

## 最佳做法和限制

### 製作

* 此 **[!UICONTROL Jump]** 活動僅適用於使用名稱空間的歷程中。
* 您只能跳至使用與來源歷程相同名稱空間的歷程。
* 您無法跳至開頭為的歷程 **區段資格** 事件。
* 您無法擁有 **[!UICONTROL Jump]** 活動和 **區段資格** 相同歷程中的事件。
* 您可以包含儘可能多的 **[!UICONTROL Jump]** 您所需的活動。 晚於 **[!UICONTROL Jump]**，您可以新增任何需要的活動。
* 您可以視需要設定任意數目的跳轉層級。 例如，歷程A跳至歷程B，而後者跳至歷程C，依此類推。
* 目標歷程也可以包含儘可能多的人 **[!UICONTROL Jump]** 活動。
* 不支援回圈模式。 無法將兩個或多個歷程連結在一起，這會造成無限回圈。 此 **[!UICONTROL Jump]** 活動設定畫面會阻止您執行此動作。

### 執行

* 當 **[!UICONTROL Jump]** 會執行活動，並觸發最新版本的目標歷程。
* 如同往常，不重複個人只能出現在相同歷程中一次。 因此，如果從來源歷程推送的個人已在目標歷程中，則該個人不會進入目標歷程。 不會在上回報任何錯誤 **[!UICONTROL Jump]** 活動，因為這是正常行為。

## 設定跳轉活動

1. 設計您的 **來源歷程**.

   ![](../assets/jump1.png)

1. 在歷程的任何步驟中，新增 **[!UICONTROL Jump]** 活動，從 **[!UICONTROL ACTIONS]** 類別。 新增標籤和說明。

   ![](../assets/jump2.png)

1. 按一下 **目標歷程** 欄位。
清單會顯示草稿、即時或測試模式中的所有歷程版本。 使用不同名稱空間或開頭為的歷程 **區段資格** 事件無法使用。 也會篩選掉會建立回圈模式的目標歷程。

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >您可以按一下 **開啟目標歷程** 圖示來在新的索引標籤中開啟目標歷程。

1. 選取您要跳至的目標歷程。
此 **第一個事件** 欄位會預先填入目標歷程第一個事件的名稱。 如果您的目標歷程包含多個事件， **[!UICONTROL Jump]** 僅允許在第一個事件上使用。

   ![](../assets/jump4.png)

1. 此 **動作引數** 區段會顯示目標事件的所有欄位。 與其他型別的動作相同，將每個欄位與來源事件或資料來源的欄位對應。 此資訊將在執行階段傳遞至目標歷程。
1. 新增後續活動以完成您的來源歷程。

   ![](../assets/jump5.png)


   >[!NOTE]
   >
   >個人的身分會自動對應。 此資訊在介面中不可見。

您的 **[!UICONTROL Jump]** 活動已設定。 當您的歷程為即時歷程或處於測試模式時，個人會到達 **[!UICONTROL Jump]** 步驟將從推送至目標歷程。

當 **[!UICONTROL Jump]** 活動是在歷程中設定，a **[!UICONTROL Jump]** 進入圖示會自動在目標歷程的開頭新增。 這可幫助您識別歷程可從外部觸發，但也可從內部觸發。 **[!UICONTROL Jump]** 活動。

![](../assets/jump7.png)

## 疑難排解

當歷程發佈或處於測試模式時，將發生錯誤，如果：
* 目標歷程已不存在
* 目標歷程為草稿、已關閉或已停止
* 如果目標歷程的第一個事件已變更且對應已中斷

![](../assets/jump6.png)
