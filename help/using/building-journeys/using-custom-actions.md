---
product: adobe campaign
title: 使用自訂動作
description: 瞭解動作活動
feature: Journeys
role: User
level: Intermediate
exl-id: 9996d1eb-ddef-46dd-aaa9-c37fa9deb2f9
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 9%

---

# 使用自訂動作 {#section_f2c_hbg_nhb}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_


活動設定窗格會顯示URL設定引數，以及為自訂動作設定的驗證引數。 [了解更多](../action/about-custom-action-configuration.md)。

## URL 組態

### 動態路徑

如果URL包含動態路徑，請在&#x200B;**[!UICONTROL Path]**&#x200B;欄位中指定路徑。

>[!NOTE]
>
>您無法在歷程中設定URL的靜態部分，但在自訂動作的全域設定中設定。 [了解更多](../action/about-custom-action-configuration.md)。

若要串連欄位和純文字字串，請使用字串函式或進階運算式編輯器中的加號(+)。 以單引號(&#39;)或雙引號(&#39;&#39;)括住純文字字串。 [了解更多](../expression/expressionadvanced.md)。

此表格顯示組態範例：

| 欄位 | 值 |
| --- | --- |
| URL | `https://xxx.yyy.com:8080/somethingstatic/` |
| 路徑 | `The id of marketingCampaign + '/messages'` |

串連的URL具有以下形式：

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;行銷活動ID\>`/messages`

![](../assets/journey-custom-action-url.png)

### 標頭

**[!UICONTROL URL Configuration]**&#x200B;區段顯示動態標頭欄位，但不顯示常數標頭欄位。 動態標頭欄位是HTTP標頭欄位，其值已設定為變數。 [了解更多](../action/about-custom-action-configuration.md)。

必要時，請指定動態標頭欄位的值：

1. 選取歷程中的自訂動作。
1. 在設定窗格中，按一下&#x200B;**[!UICONTROL URL Configuration]**&#x200B;區段中標題欄位旁的鉛筆圖示。

   ![](../assets/journey-dynamicheaderfield.png)

1. 選取欄位並按一下&#x200B;**[!UICONTROL OK]**。

## 動作引數

在&#x200B;**[!UICONTROL Action parameters]**&#x200B;區段中，您會看到定義為&#x200B;_「變數」_&#x200B;的訊息引數。 對於這些引數，您可以定義從何處取得此資訊（例如：事件、資料來源）、手動傳遞值或使用進階運算式編輯器進行進階使用案例。 進階使用案例可以是資料操控和其他函式用途。 [了解更多](../expression/expressionadvanced.md)。

**相關主題**

[設定動作](../action/about-custom-action-configuration.md)
