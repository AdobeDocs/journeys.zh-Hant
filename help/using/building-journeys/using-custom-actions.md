---
product: adobe campaign
title: 使用自訂動作
description: 了解動作活動
feature: Journeys
role: User
level: Intermediate
exl-id: 9996d1eb-ddef-46dd-aaa9-c37fa9deb2f9
source-git-commit: e71d641888caa9385d078d9c85e073b5f1ed743f
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 9%

---

# 使用自訂動作 {#section_f2c_hbg_nhb}

活動配置窗格顯示URL配置參數以及為自定義操作配置的驗證參數。 [了解更多](../action/about-custom-action-configuration.md)。

>[!NOTE]
>
>您無法在自訂動作參數中傳遞簡單集合。 不支援更複雜的收集欄位（物件陣列）。  另請注意，參數具有預期的格式(範例：字串、小數等)。 您必須小心遵守這些預期的格式。

## URL 組態

### 動態路徑

如果URL包含動態路徑，請在&#x200B;**[!UICONTROL Path]**&#x200B;欄位中指定路徑。

>[!NOTE]
>
>您無法在歷程中設定URL的靜態部分，但是在自訂動作的全域設定中。 [了解更多](../action/about-custom-action-configuration.md)。

若要串連欄位和純文字字串，請使用進階運算式編輯器中的字串函式或加號(+)。 用單引號(&#39;)或雙引號(&quot;)將純文字字串括住。 [了解更多](../expression/expressionadvanced.md)。

下表顯示配置的示例：

| 欄位 | 值 |
| --- | --- |
| URL | `https://xxx.yyy.com:8080/somethingstatic/` |
| 路徑 | `The id of marketingCampaign + '/messages'` |

串連的URL有下清單單：

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;campaign ID=&quot;&quot;>`/messages`

![](../assets/journey-custom-action-url.png)

### 標頭

**[!UICONTROL URL Configuration]**&#x200B;區段顯示動態標題欄位，但不顯示常數標題欄位。 動態標題欄位是HTTP標題欄位，其值設定為變數。 [了解更多](../action/about-custom-action-configuration.md)。

如果需要，請指定動態標題欄位的值：

1. 選取歷程中的自訂動作。
1. 在設定窗格中，按一下&#x200B;**[!UICONTROL URL Configuration]**&#x200B;區段中標題欄位旁的鉛筆圖示。

   ![](../assets/journey-dynamicheaderfield.png)

1. 選擇一個欄位，然後按一下&#x200B;**[!UICONTROL OK]**。

## 動作參數

在&#x200B;**[!UICONTROL Action parameters]**&#x200B;區段中，您會看到定義為&#x200B;_&quot;Variable&quot;_&#x200B;的訊息參數。 對於這些參數，您可以定義取得此資訊的位置(範例：事件、資料來源)、手動傳遞值，或使用進階運算式編輯器來處理進階使用案例。 進階使用案例可以是資料操作和其他函式使用。 [了解更多](../expression/expressionadvanced.md)。

**相關主題**

[設定動作](../action/about-custom-action-configuration.md)
