---
product: adobe campaign
title: 使用自訂動作
description: 瞭解操作活動
feature: Journeys
role: User
level: Intermediate
exl-id: 9996d1eb-ddef-46dd-aaa9-c37fa9deb2f9
source-git-commit: 8980df5cc238a7195f01a1631e418a8de677fbea
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 11%

---

# 使用自訂動作 {#section_f2c_hbg_nhb}

活動配置窗格顯示為自定義操作配置的URL配置參數和驗證參數。 [了解更多](../action/about-custom-action-configuration.md)。

## URL 組態

### 動態路徑

如果URL包含動態路徑，請在 **[!UICONTROL Path]** 的子菜單。

>[!NOTE]
>
>您不能在行程中設定URL的靜態部分，而是在自定義操作的全局配置中。 [了解更多](../action/about-custom-action-configuration.md)。

要連接欄位和純文字檔案字串，請使用String函式或高級表達式編輯器中的加號(+)。 將純文字檔案字串用單引號(&#39;)或雙引號(&quot;)括起來。 [了解更多](../expression/expressionadvanced.md)。

下表顯示了配置示例：

| 欄位 | 值 |
| --- | --- |
| URL | `https://xxx.yyy.com:8080/somethingstatic/` |
| 路徑 | `The id of marketingCampaign + '/messages'` |

連接的URL具有以下表單：

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;campaign id=&quot;&quot;>`/messages`

![](../assets/journey-custom-action-url.png)

### 標頭

的 **[!UICONTROL URL Configuration]** 部分顯示動態標題欄位，但不顯示常數標題欄位。 動態標頭欄位是其值配置為變數的HTTP標頭欄位。 [了解更多](../action/about-custom-action-configuration.md)。

如果需要，請指定動態標題欄位的值：

1. 選擇行程中的自定義操作。
1. 在配置窗格中，按一下中標題欄位旁邊的鉛筆表徵圖 **[!UICONTROL URL Configuration]** 的子菜單。

   ![](../assets/journey-dynamicheaderfield.png)

1. 選擇一個欄位，然後按一下 **[!UICONTROL OK]**。

## 操作參數

在 **[!UICONTROL Action parameters]** 部分，您將看到定義為 _&quot;變數&quot;_。 對於這些參數，可以定義獲取此資訊的位置(例如：事件、資料源)、手動傳遞值或使用高級表達式編輯器進行高級使用案例。 高級使用案例可以是資料操作和其他函式使用。 [了解更多](../expression/expressionadvanced.md)。

**相關主題**

[設定動作](../action/about-custom-action-configuration.md)
