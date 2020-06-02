---
title: 關於進階運算式編輯器
description: 瞭解如何建立進階運算式
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1ccf020a882c1d6d9bd00f2e9f5d6b2aee6f7829
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 2%

---


# 關於進階運算式編輯器 {#concept_uyj_trt_52b}

進階運算式編輯器可讓您在介面的各種畫面中建立進階運算式，例如在定義資料來源條件時。
此外，您每次需要定義需要特定資料處理的動作參數時，都可使用它。 您可以運用來自事件的資料或從資料來源擷取的其他資訊。 在旅程中，顯示的事件欄位清單是情境式的，並會根據旅程中新增的事件而有所不同。

進階運算式編輯器提供一組內建函式和運算子，讓您控制值並定義符合您需求的運算式。 進階運算式編輯器也可讓您定義外部資料來源參數的值、控制對應欄位和集合，例如體驗事件。

![](../assets/journey65.png)

_進階運算式編輯器介面_

進階運算式編輯器可用於：

* 建立 [資料來源](../building-journeys/condition-activity.md#about_condition) 、事件資訊的進階條件
* 定義自訂 [等待活動](../building-journeys/wait-activity.md#custom)
* 定義動作參數映射

如果可能，可以使用／按鈕在兩種模 **[!UICONTROL Advanced mode]** 式之 **[!UICONTROL Simple mode]** 間切換。 此處介紹了簡單 [模式](../building-journeys/condition-activity.md#about_condition)。

>[!NOTE]
>
>條件可在簡單或進階運算式編輯器中定義。 它們總是傳回布林類型。
>
>操作參數可通過選擇欄位或通過高級表達式編輯器來定義。 他們會根據其運算式傳回特定的資料類型。

## Accessing the advanced expression editor {#section_fdz_4nj_cjb}

您可以以不同方式訪問高級表達式編輯器：

* 當您建立資料來源條件時，可以按一下以存取進階編輯器 **[!UICONTROL Advanced mode]**。

   ![](../assets/journeyuc2_33.png)

* 當您建立自訂計時器時，會直接顯示進階編輯器。
* 映射操作參數時，按一下 **[!UICONTROL Advanced mode]**。

## 探索介面{#section_otq_tnj_cjb}

此螢幕可讓您手動編寫運算式。

![](../assets/journey70.png)

在畫面的左側會顯示可用欄位和函式：

* **[!UICONTROL Events]**: 選擇從入站事件接收的欄位之一。 顯示的事件欄位清單是內容相關的，並會根據歷程中新增的事件而有所不同。
* **[!UICONTROL Data Sources]**: 從資料來源欄位群組中的可用欄位清單中選擇。
* **[!UICONTROL Functions]**: 從可執行複雜篩選的內建函式清單中選擇。 功能依類別組織。

![](../assets/journey65.png)

自動完成機制會顯示內容相關建議。

![](../assets/journey68.png)

語法驗證機制會檢查程式碼的完整性。 錯誤會顯示在編輯器上方。

![](../assets/journey69.png)

**使用進階運算式編輯器建立條件時需要參數**

如果您從外部資料來源選取欄位，需要呼叫參數(請參閱 [](../datasource/external-data-sources.md)。 例如，在天氣相關資料來源中，常用的參數為&quot;city&quot;。 因此，您必須選擇要取得此城市參數的位置。 函式也可套用至參數，以執行格式變更或串連。

![](../assets/journeyuc2_19.png)

對於更複雜的使用案例，如果您想將資料來源的參數包含在主運算式中，則可使用「params」關鍵字來定義其值。 請參 [閱本頁](../expression/field-references.md)。
