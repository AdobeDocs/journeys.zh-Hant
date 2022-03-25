---
product: adobe campaign
solution: Journey Orchestration
title: 使用自訂動作以動態方式傳遞集合
description: 使用 Campaign v7/v8 傳送訊息
exl-id: 9ed62a74-3c51-4f15-af8a-d530ddf80b51
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 7%

---

# 使用自訂動作以動態方式傳遞集合{#passing-collection}

您可以在自定義操作參數中傳遞集合，這些參數將在運行時動態填充。 支援兩種集合：

* 簡單集合：簡單資料類型的陣列，例如，具有listString:

   ```
   {
    "deviceTypes": [
        "android",
        "ios"
    ]
   }
   ```

* 對象集合：JSON對象的陣列，例如：

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

* 目前不支援對象陣列中對象的嵌套陣列。 例如：

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
* 要使用test模式test集合，需要使用代碼視圖模式。 當前不支援業務事件的代碼視圖模式。 您只能發送包含單個元素的集合。

## 一般程式 {#general-procedure}

在本節中，我們將使用以下JSON負載示例。 這是一組對象，其中欄位是一個簡單集合。

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

您可以看到「產品」是兩個對象的陣列。 你至少需要一個對象。

1. 建立自定義操作。 請參閱[此頁面](../action/about-custom-action-configuration.md)。

1. 在 **[!UICONTROL Action parameters]** 部分，貼上JSON示例。 顯示的結構是靜態的：貼上負載時，所有欄位都定義為常數。

   ![](../assets/uc-collection-1.png)

1. 如果需要，請調整欄位類型。 集合支援以下欄位類型：listString、listInteger、listDecimal、listBoolean、listDateTime、listDateTimeOnly、listDateOnly、listOdateOnly、listObject

   >[!NOTE]
   >
   >根據有效載荷示例自動推斷欄位類型。

1. 如果要動態傳遞對象，則需要將其設定為變數。 在本示例中，我們將&quot;products&quot;設定為變數。 對象中包含的所有對象欄位都自動設定為變數。

   >[!NOTE]
   >
   >負載示例的第一個對象用於定義欄位。

1. 對於每個欄位，定義將顯示在行程畫布中的標籤。

   ![](../assets/uc-collection-2.png)

1. 建立行程並添加您建立的自定義操作。 請參閱[此頁面](../building-journeys/using-custom-actions.md)。

1. 在 **[!UICONTROL Action parameters]** 部分，使用高級表達式編輯器定義陣列參數（本例中的「products」）。

   ![](../assets/uc-collection-3.png)

1. 對於以下每個對象欄位，鍵入源XDM架構中的相應欄位名。 如果名稱相同，則不需要這樣做。 在示例中，我們只需定義「product id」和「color」。

   ![](../assets/uc-collection-4.png)

對於陣列欄位，還可以使用高級表達式編輯器執行資料操作。 在以下示例中，我們使用 [濾波器](../functions/functionfilter.md) 和 [相交](../functions/functionintersect.md) 函式：

![](../assets/uc-collection-5.png)

## 特定案例{#examples}

對於異構類型和陣列的陣列，使用listAny類型定義陣列。 您只能映射單個項，但無法將陣列更改為變數。

![](../assets/uc-collection-heterogeneous.png)

異源類型示例：

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

陣列示例：

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

[使用自定義操作](../building-journeys/using-custom-actions.md)
