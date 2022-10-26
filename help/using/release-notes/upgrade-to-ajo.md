---
title: 升級至Adobe Journey Optimizer
description: 了解如何升級至Adobe Journey Optimizer
hide: true
hidefromtoc: true
source-git-commit: e7d1b6401f03603a56d963672da1b402d0fe5e80
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 2%

---


# 將您的Journey Orchestration環境升級至Adobe Journey Optimizer{#ugrade-ajo}

## 什麼是Adobe Journey Optimizer?

Adobe Journey Optimizer是一款靈活且可擴充的應用程式，建置於Adobe Experience Platform上，可協調及提供個人化、連線、及時的客戶歷程，涵蓋所有應用程式、裝置、畫面或管&#x200B;道。

## 何謂 Journey Orchestration？

Journey Orchestration是以Adobe Experience Platform為建置基礎的服務，可讓您根據每位客戶先前的行為和偏好，量身打造個別歷程。 Journey Orchestration是Journey Optimizer的前導應用程式。

## 我為什麼要搬到Adobe Journey Optimizer?

**存取簡化的介面** 提供Experience Platform功能，讓您快速存取歷程、資料集、設定檔、警報等。 Adobe Experience Platform和Journey Orchestration之間無需再往返存取結構或資料集，一切都可直接從Adobe Journey Optimizer取得。 如需詳細資訊，請參閱 [頁面](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/user-interface.html).

<table>
<tr>
<th>變更前</th>
<th>變更後</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-1.png"><p>在Journey Orchestration中存取「歷程」、「區段」和「管理員」區段（資料來源、事件和動作）。 區段和資料集可在Adobe Experience Platform中存取。 </p></td>
<td><img src="../assets/migration-ajo-2.png"><p>存取歷程、區段、管理員、區段和資料集 <strong>Adobe Journey Optimizer</strong>. <strong>其他Adobe Experience Platform功能</strong> 也可從此存取。</p></td>
</tr>
</table>

**新報表介面** 和存取新的報表功能：

<table>
<tr>
<th>變更前</th>
<th>變更後</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-5.png"></td>
<td><img src="../assets/migration-ajo-6.png"><p><strong>全域檢視</strong> 可讓您測量在選取時段內的歷程和傳送的影響。 如需更多即時量度，您可以存取 <strong>即時檢視</strong>. 對於您歷程中使用的每個傳送通道（電子郵件、簡訊、推播）, <strong>專屬區段</strong> 可在報表中檢視量度。 唯有當您使用現成可用時，才適用 <strong>Adobe Journey Optimizer傳訊功能</strong>. 請洽詢您的客戶團隊以取得詳細資訊。</p></td>
</tr>
</table>

任何改善報表體驗或在新功能發行後加以擴充的演變，都只能在新的報表介面上使用。 開始使用它以取得更完整的Adobe Journey Optimizer體驗。

獲得其他電流的好處 **Adobe Journey Optimizer功能** 以及新推出的欄位層級存取控制和物件層級存取控制。 請洽詢您的客戶團隊以取得詳細資訊。

## 如何升級我的Journey Orchestration環境？

1. 請洽詢您的客戶團隊，以免費更新與Adobe的合約。

1. 等待工程團隊完成變更。

1. 使用Journey Optimizer的產品設定檔更新您的權限。 請參閱 [頁面](https://experienceleague.adobe.com/docs/journey-optimizer/using/administration/ootb-product-profiles.html?lang=zh-Hant).

1. 您現在可以存取Adobe Journey Optimizer!

## 常見問答

### 我需要計畫從Journey Orchestration到Adobe Journey Optimizer的任何事嗎？

不需要，不需要遷移，不需要您的工作，不需要停機，也不需要額外投資。 您只需更新與Adobe的合約，我們會完成其餘工作。 請連絡您的客戶代表，以取得如何開始此程式的指示。

### 改變之後我會失去什麼嗎？

否，您會保留所有現有的Journey Orchestration和Adobe Experience Platform物件：結構、資料集、歷程、事件、資料來源、動作。 不會遺失任何內容，所有即時歷程都會持續運作，不會中斷。

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

### 我仍在應用程式切換器中看到Journey Orchestration，這是正常嗎？

![](../assets/migration-ajo-9.png)

是的，這是正常的。 升級後，您將可將Journey Orchestration存取權保留一個月。 這可讓您有足夠的時間更新所有使用者權限，以更熟悉Adobe Journey Optimizer。 一個月後，存取權將會移除。

### 今天若將Journey Orchestration與Adobe Campaign Standard搭配使用會發生什麼事？

移至Adobe Journey Optimizer後，您仍可在Adobe Journey Optimizer中設計客戶歷程，並讓Adobe Campaign Standard傳送傳遞，以使用Journeys與Adobe Campaign Standard之間的整合。

不過，由於Adobe Journey Optimizer報表堆疊的運作方式，報表不會結合歷程和Campaign Standard資料。 Adobe Journey Optimizer報表和Adobe Campaign Standard的傳遞資訊中會提供歷程資訊。 可進行Experience Platform設定，將Adobe Campaign Standard資料傳回Adobe Experience Platform，以便供Customer Journey Analytics([了解更多](https://business.adobe.com/products/experience-platform/customer-journey-analytics.html))或其他協力廠商報表工具，例如Tableau或PowerBI。

Adobe Journey Optimizer報表最適合使用Adobe Journey Optimizer的現成可用訊息功能(可在專屬的Adobe Journey Optimizer產品中取得)。 如需如何在歷程畫布中製作訊息的詳細資訊，請參閱此 [頁面](https://experienceleague.adobe.com/docs/journey-optimizer/using/messages/messages-in-journeys.html).

請洽詢您的客戶團隊以取得詳細資訊。