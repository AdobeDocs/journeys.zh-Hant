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
ht-degree: 4%

---

# 從一個歷程跳到另一個歷程 {#jump}

的 **[!UICONTROL Jump]** 「操作」活動允許您將個人從一個旅程推向另一個旅程。 此功能允許您：

* 將複雜旅程分成若干個，簡化其設計
* 基於常用和可重複使用的行程模式構建行程

在原點行程中，只需添加 **[!UICONTROL Jump]** 活動並選擇目標行程。 當個人進入 **[!UICONTROL Jump]** 步驟，將內部事件發送到目標行程的第一事件。 如果 **[!UICONTROL Jump]** 行動成功了，個人在旅途中繼續前進。 該行為與其他操作類似。

在目標行程中，由 **[!UICONTROL Jump]** 活動會使個體在旅途中流動。

>[!NOTE]
>
>另請參閱教程視頻 [這裡](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html?lang=zh-Hant)

## 生命週期

假設您已添加 **[!UICONTROL Jump]** 在A到B的旅程中活動。旅程A **起源** 和B旅程 **目標行程**。
以下是執行過程的不同步驟：

**A旅程** 從外部事件觸發：

1. 行程A接收與個人相關的外部事件。
1. 個人到達 **[!UICONTROL Jump]** 的子菜單。
1. 將個人推至B行程，然後進入A行程的下一步， **[!UICONTROL Jump]** 的子菜單。

在B行程中，第一個事件通過 **[!UICONTROL Jump]** 行程A的活動：

1. B行程從A行程收到一個內部事件。
1. 個體開始在B旅途中流動。

>[!NOTE]
>
>B行也可以通過外部事件觸發。

## 最佳做法和限制

### 製作

* 的 **[!UICONTROL Jump]** 活動僅在使用命名空間的行程中可用。
* 您只能跳轉到使用與原始行程相同的命名空間的行程。
* 不能跳到以 **分部資格** 的子菜單。
* 您不能 **[!UICONTROL Jump]** 活動和 **分部資格** 同一旅程中的事件。
* 您可以包括 **[!UICONTROL Jump]** 在旅途中需要的活動。 在 **[!UICONTROL Jump]**，可以添加所需的任何活動。
* 可以根據需要設定任意數量的跳級。 例如，A行跳到B行，C行，等等。
* 目標行程也可包括 **[!UICONTROL Jump]** 活動。
* 不支援循環模式。 沒有辦法將兩個或兩個以上的旅程連接在一起，從而形成無限循環。 的 **[!UICONTROL Jump]** 活動配置螢幕阻止您執行此操作。

### 執行

* 當 **[!UICONTROL Jump]** 執行活動，觸發目標行程的最新版本。
* 與往常一樣，一個獨特的個體只能在同一旅程中出現一次。 因此，如果從原點行程推送的個人已在目標行程中，則該個人將不進入目標行程。 不會報告 **[!UICONTROL Jump]** 活動，因為這是正常行為。

## 配置跳轉活動

1. 設計 **起源**。

   ![](../assets/jump1.png)

1. 在旅程的任何步驟中， **[!UICONTROL Jump]** 活動，從 **[!UICONTROL ACTIONS]** 的子菜單。 添加標籤和說明。

   ![](../assets/jump2.png)

1. 在 **目標行程** 的子菜單。
該清單顯示草稿、即時或處於test模式的所有行程版本。 使用不同命名空間或以 **分部資格** 事件不可用。 也會過濾掉將建立循環模式的目標行程。

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >您可以按一下 **開啟目標行程** 表徵圖，在右側開啟新頁籤中的目標行程。

1. 選擇要跳轉到的目標行程。
的 **第一個事件** 欄位中預填目標旅程的第一個事件的名稱。 如果目標行程包括多個事件， **[!UICONTROL Jump]** 僅允許在第一個事件上。

   ![](../assets/jump4.png)

1. 的 **操作參數** 部分顯示目標事件的所有欄位。 與其它類型的操作相同，使用源事件或資料源中的欄位映射每個欄位。 此資訊將在運行時傳遞到目標行程。
1. 添加下一個活動以完成原點旅程。

   ![](../assets/jump5.png)


   >[!NOTE]
   >
   >將自動映射個人的標識。 此資訊在介面中不可見。

您 **[!UICONTROL Jump]** 已配置活動。 一旦您的旅程處於活動狀態或處於test模式，個人即可到達 **[!UICONTROL Jump]** 步驟將從目標行程推進。

當 **[!UICONTROL Jump]** 在行程中配置活動， **[!UICONTROL Jump]** 在目標行程的開始處自動添加條目表徵圖。 這有助於您確定行程可以從外部觸發，也可以從 **[!UICONTROL Jump]** 的子菜單。

![](../assets/jump7.png)

## 疑難排解

當行程發佈或處於test模式時，如果出現以下情況，則會發生錯誤：
* 目標行程不再存在
* 目標行程為草稿、關閉或停止
* 如果目標行程的第一個事件已更改，並且映射已中斷

![](../assets/jump6.png)
