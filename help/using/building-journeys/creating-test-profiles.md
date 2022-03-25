---
product: adobe campaign
title: 建立test配置檔案
description: 瞭解test配置檔案建立
exl-id: f1be46a8-04b9-4f40-b18e-9099099d2e1c
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 4%

---

# 建立測試設定檔 {#create-test-profiles}

在行程中使用test模式時，需要test配置檔案。 要瞭解如何使用test模式，請參閱 [此部分](../building-journeys/testing-the-journey.md)。

在Adobe Experience Platform建立test配置檔案有不同的方法。 在本文檔中，我們重點介紹兩種方法：上傳 [csv檔案](../building-journeys/creating-test-profiles.md#create-test-profiles-csv) 使用 [API調用](../building-journeys/creating-test-profiles.md#create-test-profiles-api)。 您還可以在資料集中上載json檔案，請參閱 [資料接收文檔](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html#add-data-to-dataset)。

這些導入方法還允許您更新配置檔案屬性。 這樣，您就可以將現有配置檔案轉換為test配置檔案。 只需使用類似的檔案或API調用，並僅包括值為&quot;true&quot;的&quot;testProfile&quot;欄位。

建立test配置檔案類似於在Adobe Experience Platform建立常規配置檔案。 有關詳細資訊，請參閱 [即時客戶概要檔案文檔](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant)。

## 先決條件{#test-profile-prerequisites}

為了能夠建立配置檔案，您首先需要在Adobe Experience Platform建立一個模式和資料集。

首先，你需要 **建立架構**。 執行以下步驟：

1. 在Adobe Experience Platform，按一下 **[!UICONTROL Schemas]**的雙曲餘切值。
   ![](../assets/test-profiles-0.png)
1. 按一下 **[!UICONTROL Create schema]**，在右上角，然後選擇一個架構類型，例如 **[!UICONTROL XDM Individual Profile]**。
   ![](../assets/test-profiles-1.png)
1. 選擇架構的名稱。
1. 在 **[!UICONTROL Mixins]** ，按一下 **[!UICONTROL Add]**。
   ![](../assets/test-profiles-1-bis.png)
1. 選擇適當的混合。 確保添加 **[!UICONTROL Profile test details]** 混音。 按一下「**[!UICONTROL Add mixin]**」。
   ![](../assets/test-profiles-1-ter.png)
混合清單顯示在架構概述螢幕上。

   ![](../assets/test-profiles-2.png)
1. 在欄位清單中，按一下要定義為主標識的欄位。
   ![](../assets/test-profiles-3.png)
1. 在 **[!UICONTROL Field properties]** 右面板，檢查 **[!UICONTROL Identity]** 和 **[!UICONTROL Primary Identity]** 選項並選擇命名空間。 如果希望主標識是電子郵件地址，請選擇 **[!UICONTROL Email]** 命名空間。 按一下「**[!UICONTROL Apply]**」。
   ![](../assets/test-profiles-4.png)
1. 選擇方案並啟用 **[!UICONTROL Profile]** 的上界 **[!UICONTROL Schema properties]**。
   ![](../assets/test-profiles-5.png)
1. 按一下「**[!UICONTROL Save]**」。

>[!NOTE]
>
>有關建立架構的詳細資訊，請參閱 [XDM文檔](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#prerequisites)。

那你需要 **建立資料集** 將在其中導入配置檔案。 執行以下步驟：

1. 在Adobe Experience Platform，按一下 **[!UICONTROL Datasets]**，然後按一下 **[!UICONTROL Create dataset]**。
   ![](../assets/test-profiles-6.png)
1. 選擇 **[!UICONTROL Create dataset from schema]**。
   ![](../assets/test-profiles-7.png)
1. 選擇以前建立的架構，然後按一下 **[!UICONTROL Next]**。
   ![](../assets/test-profiles-8.png)
1. 選擇一個名稱，然後按一下 **[!UICONTROL Finish]**。
   ![](../assets/test-profiles-9.png)
1. 啟用 **[!UICONTROL Profile]** 的雙曲餘切值。
   ![](../assets/test-profiles-10.png)

>[!NOTE]
>
> 有關建立資料集的詳細資訊，請參閱 [目錄服務文檔](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html#getting-started)。

## 使用csv檔案建立test配置檔案{#create-test-profiles-csv}

在Adobe Experience Platform，可以通過將包含不同配置檔案欄位的csv檔案上載到資料集中來建立配置檔案。 這是最簡單的方法。

1. 使用電子錶格軟體建立簡單的csv檔案。
1. 為每個所需欄位添加一列。 確保添加主標識欄位（上例中的「personID」）和「testProfile」欄位設定為「true」。
   ![](../assets/test-profiles-11.png)
1. 每個配置檔案添加一行並填入每個欄位的值。
   ![](../assets/test-profiles-12.png)
1. 將電子錶格另存為csv檔案。 確保逗號用作分隔符。
1. 在Adobe Experience Platform，按一下 **[!UICONTROL Workflows]**的雙曲餘切值。
   ![](../assets/test-profiles-14.png)
1. 選擇 **[!UICONTROL Map CSV to XDM schema]**，然後按一下 **[!UICONTROL Launch]**。
   ![](../assets/test-profiles-16.png)
1. 選擇要將配置檔案導入的資料集。 按一下「**[!UICONTROL Next]**」。
   ![](../assets/test-profiles-17.png)
1. 按一下 **[!UICONTROL Choose files]** ，然後選擇csv檔案。 上載檔案時，按一下 **[!UICONTROL Next]**。
   ![](../assets/test-profiles-18.png)
1. 將源csv欄位映射到架構欄位，然後按一下 **[!UICONTROL Finish]**。
   ![](../assets/test-profiles-19.png)
1. 資料導入開始。 狀態將從 **[!UICONTROL Processing]** 至 **[!UICONTROL Success]**。 按一下 **[!UICONTROL Preview data set]**的上界。
   ![](../assets/test-profiles-20.png)
1. 檢查test配置檔案是否已正確添加。
   ![](../assets/test-profiles-21.png)

您的test配置檔案已添加，現在可在測試行程時使用。 請參閱[本節](../building-journeys/testing-the-journey.md)。
>[!NOTE]
>
> 有關csv導入的詳細資訊，請參閱 [資料接收文檔](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html#tutorials)。

## 使用API調用建立test配置檔案{#create-test-profiles-api}

您還可以通過API調用建立test配置檔案。 請參閱此[頁面](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)。

必須使用包含「配置式test詳細資訊」混合的配置式架構。 testProfile標誌是此混合的一部分。

建立配置檔案時，確保傳遞值：testProfile = true。

請注意，您還可以更新現有配置檔案，以將其testProfile標誌更改為「true」。

下面是建立test配置檔案的API調用示例：

```
curl -X POST \
'https://dcs.adobedc.net/collection/xxxxxxxxxxxxxx' \
-H 'Cache-Control: no-cache' \
-H 'Content-Type: application/json' \
-H 'Postman-Token: xxxxx' \
-H 'cache-control: no-cache' \
-H 'x-api-key: xxxxx' \
-H 'x-gw-ims-org-id: xxxxx' \
-d '{
"header": {
"msgType": "xdmEntityCreate",
"msgId": "xxxxx",
"msgVersion": "xxxxx",
"xactionid":"xxxxx",
"datasetId": "xxxxx",
"imsOrgId": "xxxxx",
"source": {
"name": "Postman"
},
"schemaRef": {
"id": "https://example.adobe.com/mobile/schemas/xxxxx",
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"body": {
"xdmMeta": {
"schemaRef": {
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"xdmEntity": {
"_id": "xxxxx",
"_mobile":{
"ECID": "xxxxx"
},
"testProfile":true
}
}
}'
```
