---
product: adobe campaign
title: 建立測試設定檔
description: 瞭解如何建立測試設定檔
exl-id: f1be46a8-04b9-4f40-b18e-9099099d2e1c
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '681'
ht-degree: 3%

---

# 建立測試輪廓 {#create-test-profiles}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_


在歷程中使用測試模式時需要測試設定檔。 若要瞭解如何使用測試模式，請參閱[本節](../building-journeys/testing-the-journey.md)。

在Adobe Experience Platform中建立測試設定檔有不同的方式。 在本檔案中，我們著重於兩種方法：上傳[csv檔案](../building-journeys/creating-test-profiles.md#create-test-profiles-csv)和使用[API呼叫](../building-journeys/creating-test-profiles.md#create-test-profiles-api)。 您也可以上傳資料集中的json檔案，請參閱[資料擷取檔案](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html#add-data-to-dataset)。

這些匯入方法也可讓您更新設定檔屬性。 如此一來，您就可以將現有的設定檔轉換為測試設定檔。 只需使用類似的檔案或API呼叫，且僅加入值為「true」的「testProfile」欄位。

建立測試設定檔與在Adobe Experience Platform中建立一般設定檔類似。 如需詳細資訊，請參閱[即時客戶個人檔案檔案](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant)。

## 先決條件{#test-profile-prerequisites}

為了能夠建立設定檔，您首先需要在Adobe Experience Platform中建立結構描述和資料集。

首先，您需要&#x200B;**建立結構描述**。 請依照下列步驟操作：

1. 在Adobe Experience Platform中，按一下左側功能表中的&#x200B;**[!UICONTROL Schemas]**。
   ![](../assets/test-profiles-0.png)
1. 按一下右上方的&#x200B;**[!UICONTROL Create schema]**，然後選取結構描述型別，例如&#x200B;**[!UICONTROL XDM Individual Profile]**。
   ![](../assets/test-profiles-1.png)
1. 選擇結構描述的名稱。
1. 在&#x200B;**[!UICONTROL Mixins]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Add]**。
   ![](../assets/test-profiles-1-bis.png)
1. 選取適當的mixin。 請務必新增&#x200B;**[!UICONTROL Profile test details]** mixin。 按一下「**[!UICONTROL Add mixin]**」。
   ![](../assets/test-profiles-1-ter.png)
Mixin清單會顯示在架構概觀畫面上。
   ![](../assets/test-profiles-2.png)
1. 在欄位清單中，按一下要定義為主要身分的欄位。
   ![](../assets/test-profiles-3.png)
1. 在&#x200B;**[!UICONTROL Field properties]**&#x200B;右側面板中，檢查&#x200B;**[!UICONTROL Identity]**&#x200B;和&#x200B;**[!UICONTROL Primary Identity]**&#x200B;選項並選取名稱空間。 如果您希望主要身分識別是電子郵件地址，請選擇&#x200B;**[!UICONTROL Email]**&#x200B;名稱空間。 按一下「**[!UICONTROL Apply]**」。
   ![](../assets/test-profiles-4.png)
1. 選取結構描述並在&#x200B;**[!UICONTROL Schema properties]**&#x200B;中啟用&#x200B;**[!UICONTROL Profile]**選項。
   ![](../assets/test-profiles-5.png)
1. 按一下「**[!UICONTROL Save]**」。

>[!NOTE]
>
>如需建立結構描述的詳細資訊，請參閱[XDM檔案](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#prerequisites)。

然後，您需要&#x200B;**建立將匯入設定檔的資料集**。 請依照下列步驟操作：

1. 在Adobe Experience Platform中，按一下左側功能表中的&#x200B;**[!UICONTROL Datasets]**，然後按一下&#x200B;**[!UICONTROL Create dataset]**。
   ![](../assets/test-profiles-6.png)
1. 選擇&#x200B;**[!UICONTROL Create dataset from schema]**。
   ![](../assets/test-profiles-7.png)
1. 選取先前建立的結構描述，然後按一下&#x200B;**[!UICONTROL Next]**。
   ![](../assets/test-profiles-8.png)
1. 選擇名稱，然後按一下&#x200B;**[!UICONTROL Finish]**。
   ![](../assets/test-profiles-9.png)
1. 啟用&#x200B;**[!UICONTROL Profile]**選項。
   ![](../assets/test-profiles-10.png)

>[!NOTE]
>
> 如需建立資料集的詳細資訊，請參閱[目錄服務檔案](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html#getting-started)。

## 使用csv檔案建立測試設定檔{#create-test-profiles-csv}

在Adobe Experience Platform中，您可以上傳包含不同設定檔欄位的csv檔案來建立設定檔至您的資料集。 這是最簡單的方法。

1. 使用試算表軟體建立簡單的csv檔案。
1. 為每個所需欄位新增一欄。 請務必新增主要身分欄位（以上範例中為「personID」），並將「testProfile」欄位設為「true」。
   ![](../assets/test-profiles-11.png)
1. 為每個設定檔新增一行，並填寫每個欄位的值。
   ![](../assets/test-profiles-12.png)
1. 將試算表儲存為csv檔案。 請務必使用逗號做為分隔符號。
1. 在Adobe Experience Platform中，按一下左側功能表中的&#x200B;**[!UICONTROL Workflows]**。
   ![](../assets/test-profiles-14.png)
1. 選擇&#x200B;**[!UICONTROL Map CSV to XDM schema]**，然後按一下&#x200B;**[!UICONTROL Launch]**。
   ![](../assets/test-profiles-16.png)
1. 選取您要將設定檔匯入的資料集。 按一下「**[!UICONTROL Next]**」。
   ![](../assets/test-profiles-17.png)
1. 按一下&#x200B;**[!UICONTROL Choose files]**&#x200B;並選取您的csv檔案。 上傳檔案時，按一下&#x200B;**[!UICONTROL Next]**。
   ![](../assets/test-profiles-18.png)
1. 將來源csv欄位對應到結構描述欄位，然後按一下&#x200B;**[!UICONTROL Finish]**。
   ![](../assets/test-profiles-19.png)
1. 資料匯入隨即開始。 狀態將從&#x200B;**[!UICONTROL Processing]**&#x200B;移至&#x200B;**[!UICONTROL Success]**。 按一下右上方的&#x200B;**[!UICONTROL Preview data set]**。
   ![](../assets/test-profiles-20.png)
1. 檢查測試設定檔是否已正確新增。
   ![](../assets/test-profiles-21.png)

您的測試設定檔已新增，現在可用於測試歷程。 請參閱[本節](../building-journeys/testing-the-journey.md)。
>[!NOTE]
>
> 如需csv匯入的詳細資訊，請參閱[資料擷取檔案](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html#tutorials)。

## 使用API呼叫建立測試設定檔{#create-test-profiles-api}

您也可以透過API呼叫建立測試設定檔。 請參閱此[頁面](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant)。

您必須使用包含「設定檔測試詳細資料」mixin的設定檔結構描述。 testProfile旗標是此mixin的一部分。

建立設定檔時，請務必傳遞值： testProfile = true。

請注意，您也可以更新現有的設定檔，將其testProfile標幟變更為「true」。

以下為建立測試設定檔的API呼叫範例：

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
