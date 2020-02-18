---
title: 發行說明 年
description: 瞭解版本注意事項
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
source-git-commit: 8023d7780d43f1de4447c63568f641ce204722c7

---


# 發行說明 {#release-notes}

本頁列出Journey Orchestration的所有新功能和改進。
您也可以參閱「檔案 [更新」](../release-notes/documentation-updates.md)。

## 第1季發行- 2019年2月 {#q1-release---february-2019}

**時區管理**

時區現在由歷程層級管理。 在歷程屬性中新增了兩個參數：

* 「 **時區** 」下拉式清單可讓您選取特定時區。 依預設，會使用瀏覽器的時區。

* 「描 **述檔時區** 」核取方塊可讓您使用進入歷程之人員的「體驗平台描述檔」時區（如果有的話）。 如果不是，則會使用下拉式清單中定義的時區。 此功能與沒有命名空間的歷程不相容。

**內容相關說明**

現在，不同的「歷程協調」螢幕上都提供內容相關的說明功能。 這表示，只要按一下，您就可以直接存取您目前使用之功能的相關檔案。

若要顯示內容相關說明，請按一下畫面右上角的「i」圖示。

目前，此功能可在「首頁」、「資料來源」、「事件」和「動作」清單畫面中使用。

**其他變更**

* 在測試模式中，新參數可讓您定義時間間隔。  等待時間的活動可以持續。 這可讓您快速存取測試結果。

* 在測試模式中，您現在可以觸發歷程中的所有事件。


* 新參數可讓您定義時間間隔。  等待時間的活動可以持續。 這可讓您快速存取測試結果。

* Journeys Orchestration現已在EMEA地區推出。

* 浮動視窗中的新圖示，可顯示或不可用項目。 sans命名空間。 par default.

* 畫布、解析、小吃icone、qui dit disconnected node。

* 短切C字列

* 浮動視窗UI,icone de search results

* Pouvoir capper les call a des APIS externes(data sources ou actions)。 marque n accepte que 500 calls par seconde, elle pourra mettre un capping a 500 calls seconds qui evite de surcharger system de loyalty tiers

* 日誌記錄。 前衛狀態=錯誤。 在阿巴拉契亞山脈上。 Possibilityé de voir code erreur phase qu&#39;à renvoyé le systeme. -> ds un test en cas d&#39;erreur, systeme tiers, error code, error response.

* 停止刪除旅程

* 旅程：版本1 il met is latest

火星一號。


## 正式發行- 2019年12月 {#ga-release---december-2019}

歷程協調現在正式推出。

運用儲存在事件或資料來源中的情境資料，建立即時協調使用案例。

Journey Orchestration可讓您即時協調，並運用來自活動的情境式資料、來自Adobe Experience Platform的資訊或來自協力廠商API服務的資料。 應用程式會根據消費者的描述檔和行為，在稱為歷程的多步驟流程中，決定下一個消費者專屬的最佳動作。 這包括最佳時機和動作類型，例如透過Adobe Campaign standard交易訊息功能（需要Adobe Campaign Standard）向消費者傳送推播通知或通知協力廠商系統。 這些決定是根據規則和Sensei得分做出的。

[進一步瞭解](../action/working-with-adobe-campaign.md) 「歷程協調」。

其他資源：

* [教學課程](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [社群](https://www.adobe.com/go/journeyorchestrationcommunity)