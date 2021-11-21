---
product: adobe campaign
title: 建立測試設定檔
description: 了解測試設定檔建立
exl-id: f1be46a8-04b9-4f40-b18e-9099099d2e1c
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 3%

---

# 建立測試設定檔 {#create-test-profiles}

在歷程中使用測試模式時，需要測試設定檔。 若要了解如何使用測試模式，請參閱 [本節](../building-journeys/testing-the-journey.md).

在Adobe Experience Platform中建立測試設定檔有不同的方式。 在本檔案中，我們著重於兩種方法：上傳 [csv檔案](../building-journeys/creating-test-profiles.md#create-test-profiles-csv) 和使用 [API呼叫](../building-journeys/creating-test-profiles.md#create-test-profiles-api). 您也可以上傳資料集中的JSON檔案，請參閱 [資料擷取檔案](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html#add-data-to-dataset).

這些匯入方法也可讓您更新設定檔屬性。 這樣，您就可以將現有設定檔轉換為測試設定檔。 只要使用類似的檔案或API呼叫，並僅包含「testProfile」欄位（其值為「true」）即可。

建立測試設定檔類似於在Adobe Experience Platform中建立一般設定檔。 如需詳細資訊，請參閱 [即時客戶個人檔案檔案檔案](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant).

## 先決條件{#test-profile-prerequisites}

若要建立設定檔，您必須先在Adobe Experience Platform中建立結構和資料集。

首先，你需要 **建立結構**. 請依照下列步驟操作：

1. 在Adobe Experience Platform中，按一下 **[!UICONTROL Schemas]**，即可取得Advertising Cloud的說明。
   ![](../assets/test-profiles-0.png)
1. 按一下 **[!UICONTROL Create schema]**，然後選取結構類型，例如 **[!UICONTROL XDM Individual Profile]**.
   ![](../assets/test-profiles-1.png)
1. 選擇架構的名稱。
1. 在 **[!UICONTROL Mixins]** ，按一下 **[!UICONTROL Add]**.
   ![](../assets/test-profiles-1-bis.png)
1. 選取適當的混合。 請務必新增 **[!UICONTROL Profile test details]** 米辛。 按一下「**[!UICONTROL Add mixin]**」。
   ![](../assets/test-profiles-1-ter.png)
mixin清單會顯示在結構概述畫面上。

   ![](../assets/test-profiles-2.png)
1. 在欄位清單中，按一下您要定義為主要身分的欄位。
   ![](../assets/test-profiles-3.png)
1. 在 **[!UICONTROL Field properties]** 右面板，檢查 **[!UICONTROL Identity]** 和 **[!UICONTROL Primary Identity]** 選項並選取命名空間。 如果您希望主要身分成為電子郵件地址，請選擇 **[!UICONTROL Email]** 命名空間。 按一下「**[!UICONTROL Apply]**」。
   ![](../assets/test-profiles-4.png)
1. 選擇架構並啟用 **[!UICONTROL Profile]** 選項 **[!UICONTROL Schema properties]**.
   ![](../assets/test-profiles-5.png)
1. 按一下「**[!UICONTROL Save]**」。

>[!NOTE]
>
>有關架構建立的詳細資訊，請參閱 [XDM檔案](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#prerequisites).

那你需要 **建立資料集** 中匯入設定檔。 請依照下列步驟操作：

1. 在Adobe Experience Platform中，按一下 **[!UICONTROL Datasets]**，在左側功能表中，然後按一下 **[!UICONTROL Create dataset]**.
   ![](../assets/test-profiles-6.png)
1. 選擇 **[!UICONTROL Create dataset from schema]**.
   ![](../assets/test-profiles-7.png)
1. 選取先前建立的架構，然後按一下 **[!UICONTROL Next]**.
   ![](../assets/test-profiles-8.png)
1. 選擇名稱，然後按一下 **[!UICONTROL Finish]**.
   ![](../assets/test-profiles-9.png)
1. 啟用 **[!UICONTROL Profile]** 選項。
   ![](../assets/test-profiles-10.png)

>[!NOTE]
>
> 如需建立資料集的詳細資訊，請參閱 [目錄服務檔案](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html#getting-started).

## 使用csv檔案建立測試設定檔{#create-test-profiles-csv}

在Adobe Experience Platform中，您可以將包含不同設定檔欄位的csv檔案上傳至資料集，以建立設定檔。 這是最簡單的方法。

1. 使用試算表軟體建立簡單的csv檔案。
1. 為每個需要的欄位新增一欄。 請務必新增主要身分欄位（上述範例中為「personID」），以及設為「true」的「testProfile」欄位。
   ![](../assets/test-profiles-11.png)
1. 為每個設定檔新增一行，並填入每個欄位的值。
   ![](../assets/test-profiles-12.png)
1. 將試算表儲存為CSV檔案。 請確定逗號是分隔符號。
1. 在Adobe Experience Platform中，按一下 **[!UICONTROL Workflows]**，即可取得Advertising Cloud的說明。
   ![](../assets/test-profiles-14.png)
1. 選擇 **[!UICONTROL Map CSV to XDM schema]**，然後按一下 **[!UICONTROL Launch]**.
   ![](../assets/test-profiles-16.png)
1. 選取您要將設定檔匯入的資料集。 按一下「**[!UICONTROL Next]**」。
   ![](../assets/test-profiles-17.png)
1. 按一下 **[!UICONTROL Choose files]** 並選取您的csv檔案。 上傳檔案時，按一下 **[!UICONTROL Next]**.
   ![](../assets/test-profiles-18.png)
1. 將來源csv欄位對應至結構欄位，然後按一下 **[!UICONTROL Finish]**.
   ![](../assets/test-profiles-19.png)
1. 資料匯入開始。 狀態會從 **[!UICONTROL Processing]** to **[!UICONTROL Success]**. 按一下 **[!UICONTROL Preview data set]**，位於右上角。
   ![](../assets/test-profiles-20.png)
1. 檢查測試設定檔是否已正確新增。
   ![](../assets/test-profiles-21.png)

系統會新增您的測試設定檔，現在可用於測試歷程。 請參閱[本節](../building-journeys/testing-the-journey.md)。
>[!NOTE]
>
> 如需csv匯入的詳細資訊，請參閱 [資料擷取檔案](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html#tutorials).

## 使用API呼叫建立測試設定檔{#create-test-profiles-api}

您也可以透過API呼叫建立測試設定檔。 請參閱此[頁面](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)。

您必須使用包含「設定檔測試詳細資料」的設定檔結構混合。 testProfile旗標是此混合的一部分。

建立設定檔時，請務必傳遞值：testProfile = true。

請注意，您也可以更新現有的設定檔，將其testProfile標幟變更為「true」。

以下是建立測試設定檔的API呼叫範例：

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
