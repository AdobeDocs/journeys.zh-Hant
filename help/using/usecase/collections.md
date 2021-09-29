---
product: adobe campaign
solution: Journey Orchestration
title: 使用自訂動作以動態方式傳遞集合
description: 使用 Campaign v7/v8 傳送訊息
exl-id: 8832d306-5842-4be5-9fb9-509050fcbb01
source-git-commit: 5fa7df4f2e778c0b0fd31d81edab34e86ee40c47
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 4%

---


# 使用自訂動作以動態方式傳遞集合{#passing-collection}

您可以在自訂動作參數中傳遞集合，這些參數將在執行階段動態填入。 支援兩種集合：

* 簡單集合：簡單資料類型的陣列，例如，具有listString:

   ```
   {
    "deviceTypes": [
        "android",
        "ios"
    ]
   }
   ```

* 對象集合：JSON物件的陣列，例如：

   ```
   {
   "products":[
      {
         "id":"productA",
         "name":"A",
         "price":20.1
      },
      {
         "id":"productB",
         "name":"B",
         "price":10.0
      },
      {
         "id":"productC",
         "name":"C",
         "price":5.99
      }
    ]
   }
   ```

## 限制 {#limitations}

* 不支援包含子對象的對象陣列。 例如：

   ```
   {
   "products":[
     {
        "id":"productA",
        "name":"A",
        "details": {
        "color":"blue"
        },
        "price":20.0
     }
    ]
   }
   ```

* 目前不支援物件陣列內的巢狀物件陣列。 例如：

   ```
   {
   "products":[
     {
        "id":"productA",
        "name":"A",
        "price":20,
        "locations": [{"name": "Paris"}, {"name": "London"}]
     },
    ]
   }
   ```
* 若要使用測試模式來測試集合，您必須使用程式碼檢視模式。 目前商業事件不支援程式碼檢視模式。 您只能傳送包含單一元素的集合。

## 一般程式 {#general-procedure}

在本節中，我們將使用下列JSON裝載範例。 這是一組物件，其欄位為簡單集合。

```
{
  "ctxt": {
    "products": [
      {
        "id": "productA",
        "name": "A",
        "price": 20.1,
        "color":"blue",
        "locations": [
          "Paris",
          "London"
        ]
      },
      {
        "id": "productB",
        "name": "B",
        "price": 10.99
      }
    ]
  }
}
```

您可以看到「products」是兩個物件的陣列。 你至少需要一個對象。

1. 建立自訂動作。 請參閱[此頁面](../action/about-custom-action-configuration.md)。

1. 在&#x200B;**[!UICONTROL Action parameters]**&#x200B;區段中，貼上JSON範例。 顯示的結構為靜態：貼上裝載時，所有欄位都定義為常數。

   ![](../assets/uc-collection-1.png)

1. 如有需要，請調整欄位類型。 集合支援下列欄位類型：listString, listInteger, listDecimal, listBoolean, listDateTime, listDateTimeOnly, listDateOnly, listDateOnly, listOntly

   >[!NOTE]
   >
   >欄位類型會根據裝載範例自動推斷。

1. 如果要動態傳遞對象，則需要將它們設定為變數。 在此範例中，我們將「products」設為變數。 物件中包含的所有物件欄位都會自動設為變數。

   >[!NOTE]
   >
   >有效負載範例的第一個物件可用來定義欄位。

1. 針對每個欄位，定義將顯示在歷程畫布中的標籤。

   ![](../assets/uc-collection-2.png)

1. 建立您的歷程，並新增您建立的自訂動作。 請參閱[此頁面](../building-journeys/using-custom-actions.md)。

1. 在&#x200B;**[!UICONTROL Action parameters]**&#x200B;區段中，使用進階運算式編輯器定義陣列參數（本範例中為&quot;products&quot;）。

   ![](../assets/uc-collection-3.png)

1. 對於下列每個物件欄位，從來源XDM架構中輸入對應的欄位名稱。 如果名稱相同，則不需要。 在我們的範例中，我們只需定義「產品id」和「color」。

   ![](../assets/uc-collection-4.png)

對於陣列欄位，您也可以使用進階運算式編輯器來執行資料操作。 在以下範例中，我們使用[filter](https://git.corp.adobe.com/AdobeDocs/journeys.en/blob/fvi-21.9/help/using/functions/functionfilter.md)和[intersect](https://git.corp.adobe.com/AdobeDocs/journeys.en/blob/fvi-21.9/help/using/functions/functiontintersect.md)函式：

![](../assets/uc-collection-5.png)

## 特定案例{#examples}

對於異構類型和陣列，陣列由listAny類型定義。 您只能映射個別項目，但無法將陣列變更為變數。

![](../assets/uc-collection-heterogeneous.png)

異質類型的示例：

```
{
    "data_mixed-types": [
        "test",
        "test2",
        null,
        0
    ]
}
```

陣列的範例：

```
{
    "data_multiple-arrays": [
        [
            "test",
            "test1",
            "test2"
        ]
    ]
}
```

**相關主題**

[使用自訂動作](../building-journeys/using-custom-actions.md)