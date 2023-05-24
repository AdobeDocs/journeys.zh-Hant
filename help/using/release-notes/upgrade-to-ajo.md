---
title: 升級到Adobe Journey Optimizer
description: 瞭解如何升級到Adobe Journey Optimizer
hide: true
hidefromtoc: true
exl-id: 887fd3bb-bcd3-4a6d-9817-43049c51ecba
source-git-commit: 3e9ff02cecfe85ea38cce4b0d241156f6209202f
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 2%

---

# 將Journey Orchestration環境升級到Adobe Journey Optimizer{#ugrade-ajo}

## 什麼是Adobe Journey Optimizer?

Adobe Journey Optimizer是一個靈活且可擴展的應用程式，本地構建在Adobe Experience Platform上，用於組織和提供跨任何應用、設備、螢幕或渠道的個性化、連接且及時的客戶&#x200B;旅程。

## 何謂 Journey Orchestration？

Journey Orchestration是一種基於Adobe Experience Platform的服務，它允許您根據每個客戶以前的行為和偏好為其定制單獨的行程。 Journey Orchestration是Journey Optimizer的先兆。

## 我為什麼要搬去Adobe Journey Optimizer?

**訪問簡化的介面** Experience Platform功能可快速訪問行程、資料集、配置檔案、警報等。 不必再在Adobe Experience Platform和Journey Orchestration之間來回訪問模式或資料集了，一切都可直接從Adobe Journey Optimizer獲得。 有關詳細資訊，請參閱 [頁](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/user-interface.html)。

<table>
<tr>
<th>變更前</th>
<th>變更後</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-1.png"><p>訪問Journey Orchestration中的Journeys、Segments和Admin節（資料源、事件和操作）。 在Adobe Experience Platform，可以訪問資料段和資料集。 </p></td>
<td><img src="../assets/migration-ajo-2.png"><p>訪問Gourneys 、 Segments 、 Admin 、 Segments和Datasets 、 <strong>都在Adobe Journey Optimizer</strong>。 <strong>其他Adobe Experience Platform功能</strong> 也可以訪問。</p></td>
</tr>
</table>

**新建報告介面** 和訪問新的報告功能：

<table>
<tr>
<th>變更前</th>
<th>變更後</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-5.png"></td>
<td><img src="../assets/migration-ajo-6.png"><p><strong>全局視圖</strong> 允許您測量所選時段內的行程和交付的影響。 對於更多即時度量，您可以訪問 <strong>即時視圖</strong>。 對於您的行程中使用的每個傳送通道（電子郵件、簡訊、推送）, <strong>專用段</strong> 可在報告中查看度量。 僅當您使用現成 <strong>Adobe Journey Optimizer消息傳遞功能</strong>。 請聯繫您的客戶團隊以瞭解詳細資訊。</p></td>
</tr>
</table>

任何改進報告體驗或在新功能發佈後豐富報告體驗的演變，都只能在新報告介面上提供。 開始使用它獲得更完整的Adobe Journey Optimizer體驗。

獲取其他電流的益處 **Adobe Journey Optimizer特徵** 以及新的如欄位級訪問控制和對象級訪問控制。 請聯繫您的客戶團隊以獲取詳細資訊。

## 如何升級我的Journey Orchestration環境？

1. 聯繫您的客戶團隊以更新您的協定和Adobe。

1. 等待我們的工程團隊完成更改。

1. 使用Journey Optimizer的產品配置檔案更新您的權限。 請參閱此 [頁](https://experienceleague.adobe.com/docs/journey-optimizer/using/administration/ootb-product-profiles.html?lang=zh-Hant)。

1. 你現在可以進入Adobe Journey Optimizer!

## 常見問答

### 我需要計畫什麼，從Journey Orchestration到Adobe Journey Optimizer?

不，不需要遷移，不需要您的工作，不需要停機，也不需要額外投資。 您只需用Adobe更新您的協定，我們將完成其餘工作。 請聯繫您的客戶代表，瞭解有關如何啟動此過程的說明。

### 換衣服後我會失去什麼嗎？

不，您將保留所有現有Journey Orchestration和Adobe Experience Platform對象：模式、資料集、行程、事件、資料源、操作。 不會失去任何東西，所有直播旅程將繼續不中斷地工作。

<table>
<tr>
<th>變更前</th>
<th>變更後</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-7.png"></td>
<td><img src="../assets/migration-ajo-8.png"></td>
</tr>
</table>

### 我仍然在應用程式切換器中看到Journey Orchestration，它正常嗎？

![](../assets/migration-ajo-9.png)

是的，這很正常。 升級後，您仍可能會看到Journey Orchestration項幾天。 請用Journey Optimizer。

### 如果我今天用Journey Orchestration和Adobe Campaign Standard?

通過遷至Adobe Journey Optimizer，您仍然能夠利用Gourneys和Adobe Campaign Standard之間的整合，即設計您在Adobe Journey Optimizer的客戶行程，並讓Adobe Campaign Standard發送交貨。

但是，由於Adobe Journey Optimizer報告棧的工作方式，報告不會將Journey和Campaign Standard資料結合起來。 旅程資訊將在Adobe Journey Optimizer的報告和Adobe Campaign Standard的遞送資訊中提供。 可以配置Experience Platform，將Adobe Campaign Standard資料帶回Adobe Experience Platform，供Customer Journey Analytics使用([瞭解更多](https://business.adobe.com/products/experience-platform/customer-journey-analytics.html))或其他第三方報告工具，如Tableau或PowerBI。

Adobe Journey Optimizer報告，在使用Adobe Journey Optimizer的開箱即用消息傳遞功能(在Adobe Journey Optimizer的專用產品中提供)時，最佳操作。 有關如何在行程畫布中創作消息的詳細資訊，請參閱此 [頁](https://experienceleague.adobe.com/docs/journey-optimizer/using/messages/messages-in-journeys.html)。

請聯繫您的客戶團隊以瞭解詳細資訊。
