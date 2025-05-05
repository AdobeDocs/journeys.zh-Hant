---
product: adobe campaign
title: 關於Journey Orchestration事件的ExperienceEvent結構
description: 瞭解適用於Journey Orchestration事件的ExperienceEvent結構描述
feature: Journeys
role: User
level: Intermediate
exl-id: ffec0d42-8632-4806-97df-da2a2372ca53
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 1%

---

# 關於[!DNL Journey Orchestration]事件的ExperienceEvent結構描述


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_



[!DNL Journey Orchestration]事件是指透過串流擷取傳送至Adobe Experience Platform的XDM體驗事件。

因此，為[!DNL Journey Orchestration]設定事件的重要先決條件是，您熟悉Adobe Experience Platform的Experience Data Model （或XDM）、如何組成XDM Experience Event結構描述，以及如何將XDM格式的資料串流到Adobe Experience Platform。

## [!DNL Journey Orchestration]個事件的結構描述需求

為[!DNL Journey Orchestration]設定事件的第一步是確保您已定義代表該事件的XDM結構描述，以及已建立資料集以在Adobe Experience Platform上記錄該事件的執行個體。 嚴格來說，沒有必要為事件建立資料集，但將事件傳送至特定資料集可讓您維護使用者的事件歷史記錄，以供日後參考和分析，因此總是不錯的做法。 如果您還沒有適合事件的結構描述和資料集，這兩項工作都可以在Adobe Experience Platform網頁介面中完成。

![](../assets/schema1.png)

將用於[!DNL Journey Orchestration]事件的任何XDM結構描述都應符合下列要求：

* 結構描述必須是XDM ExperienceEvent類別。

  ![](../assets/schema2.png)

* 對於系統產生的事件，結構描述必須包括Orchestration eventID mixin。 [!DNL Journey Orchestration]使用此欄位來識別歷程中使用的事件。

  ![](../assets/schema3.png)

* 宣告識別事件主體所需的身分欄位。 如果未指定身分，則可使用身分對應。 不建議採用此做法。

  ![](../assets/schema4.png)

* 如果您希望這些資料稍後可在歷程中查詢，請標籤設定檔的結構描述和資料集。

  ![](../assets/schema5.png)

  ![](../assets/schema6.png)

* 您可以隨意加入資料欄位，以擷取您要與事件一併加入的任何其他內容資料，例如關於使用者的資訊、產生事件的裝置、位置或與事件相關的任何其他有意義的情況。

  ![](../assets/schema7.png)

  ![](../assets/schema8.png)

## 利用結構描述關係{#leverage_schema_relationships}

Adobe Experience Platform可讓您定義結構描述之間的關係，以便將一個資料集用作另一個資料集的查詢表。

假設您的品牌資料模型有一個結構描述擷取購買。 您也有產品目錄的結構描述。 您可以擷取購買結構描述中的產品ID，並使用關係從產品目錄中查詢更完整的產品詳細資訊。 舉例來說，這可讓您為所有購買筆記型電腦的客戶建立區段，而不需明確列出所有筆記型電腦ID，或擷取異動系統中的每個單一產品詳細資訊。

若要定義關係，來源結構描述中需要有專用欄位，在此案例中是購買結構描述中的產品ID欄位。 此欄位需要參考目的地結構描述中的產品ID欄位。 必須為設定檔啟用來源和目的地表格，而且目的地結構描述必須將這個通用欄位定義為其主要身分。

以下是為設定檔啟用的產品目錄結構描述，其產品ID已定義為主要身分。

![](../assets/schema9.png)

以下是購買結構描述，其關係定義在產品ID欄位上。

![](../assets/schema10.png)

>[!NOTE]
>
>在[Experience Platform檔案](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/configure-relationships-between-schemas.html?lang=zh-Hant)中進一步瞭解結構描述關係。

在Journey Orchestration中，您可以善用連結表格中的所有欄位：

* 設定單一事件時，[瞭解詳情](../event/experience-event-schema.md#unitary_event_configuration)
* 在歷程中使用條件時，[瞭解詳情](../event/experience-event-schema.md#journey_conditions_using_event_context)
* 在自訂動作個人化中，[瞭解詳情](../event/experience-event-schema.md#custom_action_personalization_with_journey_event_context)

### 單一事件設定{#unitary_event_configuration}

連結的結構描述欄位可在單一事件設定中使用：

* 瀏覽事件設定畫面中的事件結構欄位時。
* 定義系統產生事件的條件時。

![](../assets/schema11.png)

連結的欄位無法使用：

* 在事件索引鍵公式中
* 在事件id條件中（規則型事件）

若要瞭解如何設定單一事件，請參閱此[頁面](../event/about-creating.md)。

### 使用事件內容的歷程條件{#journey_conditions_using_event_context}

您可以使用查詢表格中的資料，連結至用於條件建置之歷程中的事件（運算式編輯器）。

在歷程中新增條件、編輯運算式，並在運算式編輯器中展開事件節點。

![](../assets/schema12.png)

若要瞭解如何定義歷程條件，請參閱此[頁面](../building-journeys/condition-activity.md)。

### 使用歷程事件內容的動作個人化{#custom_action_personalization_with_journey_event_context}

設定歷程動作活動的動作引數時，可使用連結的欄位。

![](../assets/schema13.png)

若要瞭解如何使用自訂動作，請參閱此[頁面](../building-journeys/using-custom-actions.md)。

