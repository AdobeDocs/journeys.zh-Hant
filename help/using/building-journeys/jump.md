---
product: adobe campaign
title: 從一個歷程跳到另一個歷程
description: 從一個歷程跳到另一個歷程
feature: 歷程
role: User
level: Intermediate
exl-id: 520376aa-2cb5-46d6-8f21-3e03544f5da1
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 4%

---

# 從一個歷程跳到另一個歷程 {#jump}

**[!UICONTROL Jump]**&#x200B;動作活動可讓您將個人從一個歷程推送至另一個歷程。 此功能可讓您：

* 將複雜的歷程分割為數個歷程，以簡化其設計
* 根據常見且可重複使用的歷程模式建立歷程

在來源歷程中，只需新增&#x200B;**[!UICONTROL Jump]**&#x200B;活動並選取目標歷程即可。 當個人進入&#x200B;**[!UICONTROL Jump]**&#x200B;步驟時，內部事件會傳送至目標歷程的第一個事件。 如果&#x200B;**[!UICONTROL Jump]**&#x200B;動作成功，個人會繼續在歷程中進行。 此行為與其他動作類似。

在目標歷程中，**[!UICONTROL Jump]**&#x200B;活動內部觸發的第一個事件將使歷程中的個別流量。

>[!NOTE]
>
>另請參閱教學課程影片[這裡](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html?lang=zh-Hant)

## 生命週期

假設您已將歷程A中的&#x200B;**[!UICONTROL Jump]**&#x200B;活動新增至歷程B。歷程A是&#x200B;**origin journey**&#x200B;和歷程B，即&#x200B;**target歷程**。
以下是執行程式的不同步驟：

**從外** 部事件觸發的歷程：

1. 歷程A會接收與個人相關的外部事件。
1. 個人達到&#x200B;**[!UICONTROL Jump]**&#x200B;步驟。
1. 個人會推送至歷程B，並在&#x200B;**[!UICONTROL Jump]**&#x200B;步驟之後繼續前往歷程A的後續步驟。

在歷程B中，第一個事件是透過歷程A的&#x200B;**[!UICONTROL Jump]**&#x200B;活動從內部觸發：

1. 歷程B從歷程A收到內部事件。
1. 個人開始在歷程B中流動。

>[!NOTE]
>
>歷程B也可透過外部事件觸發。

## 最佳做法和限制

### 製作

* **[!UICONTROL Jump]**&#x200B;活動僅適用於使用命名空間的歷程。
* 您只能跳至使用與來源歷程相同命名空間的歷程。
* 您無法跳至以&#x200B;**區段資格**&#x200B;事件開頭的歷程。
* 您無法在相同歷程中擁有&#x200B;**[!UICONTROL Jump]**&#x200B;活動和&#x200B;**區段資格**&#x200B;事件。
* 您可以在歷程中納入所需的&#x200B;**[!UICONTROL Jump]**&#x200B;活動。 在&#x200B;**[!UICONTROL Jump]**&#x200B;之後，您可以新增任何需要的活動。
* 您可以視需要擁有任意數量的跳級。 例如，歷程A會跳至歷程B，這會跳至歷程C，以此類推。
* 目標歷程也可視需要包含多個&#x200B;**[!UICONTROL Jump]**&#x200B;活動。
* 不支援循環模式。 無法將兩個或多個歷程連結在一起，進而產生無限回圈。 **[!UICONTROL Jump]**&#x200B;活動配置螢幕阻止您執行此操作。

### 執行

* 執行&#x200B;**[!UICONTROL Jump]**&#x200B;活動時，會觸發目標歷程的最新版本。
* 與往常一樣，獨特的個人只能出現在相同歷程中一次。 因此，如果從來源歷程推送的個人已在目標歷程中，則個人不會進入目標歷程。 不會回報&#x200B;**[!UICONTROL Jump]**&#x200B;活動的錯誤，因為這是正常行為。

## 配置跳轉活動

1. 設計您的&#x200B;**origin歷程**。

   ![](../assets/jump1.png)

1. 在歷程的任何步驟中，從&#x200B;**[!UICONTROL ACTIONS]**&#x200B;類別新增&#x200B;**[!UICONTROL Jump]**&#x200B;活動。 新增標籤和說明。

   ![](../assets/jump2.png)

1. 在&#x200B;**Target歷程**欄位內按一下。
清單會顯示草稿、即時或處於測試模式的所有歷程版本。 無法使用使用不同命名空間或以**區段資格**&#x200B;事件開頭的歷程。 也會篩選掉會建立回圈模式的Target歷程。

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >您可以按一下右側的&#x200B;**開啟目標歷程**&#x200B;圖示，在新索引標籤中開啟目標歷程。

1. 選取您要跳至的目標歷程。
**第一個事件**&#x200B;欄位會預先填入目標歷程第一個事件的名稱。 如果您的目標歷程包含多個事件，則僅允許在第一個事件上使用&#x200B;**[!UICONTROL Jump]**。

   ![](../assets/jump4.png)

1. **動作參數**&#x200B;區段會顯示目標事件的所有欄位。 以與其他類型動作相同的方式，將每個欄位與來源事件或資料來源的欄位對應。 這些資訊會在執行階段傳遞至目標歷程。
1. 新增下一個活動以完成您的來源歷程。

   ![](../assets/jump5.png)


   >[!NOTE]
   >
   >個人身分會自動對應。 此資訊在介面中不可見。

已設定您的&#x200B;**[!UICONTROL Jump]**&#x200B;活動。 當您的歷程為即時或處於測試模式時，到達&#x200B;**[!UICONTROL Jump]**&#x200B;步驟的個人將會從推送至目標歷程。

在歷程中設定&#x200B;**[!UICONTROL Jump]**&#x200B;活動時，會在目標歷程的開頭自動新增&#x200B;**[!UICONTROL Jump]**&#x200B;登入圖示。 這可協助您識別歷程可從外部觸發，也可從&#x200B;**[!UICONTROL Jump]**&#x200B;活動從內部觸發。

![](../assets/jump7.png)

## 疑難排解

歷程發佈或處於測試模式時，若發生下列情況，即會發生錯誤：
* target歷程已不存在
* 目標歷程為草稿、關閉或停止
* 如果target歷程的第一個事件已變更，且對應中斷

![](../assets/jump6.png)
