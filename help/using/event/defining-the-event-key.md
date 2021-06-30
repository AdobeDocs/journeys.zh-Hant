---
product: adobe campaign
title: 定義事件鍵
description: 了解如何定義事件索引鍵
feature: 歷程
role: Business Practitioner
level: Intermediate
exl-id: 79bcf562-f971-42f1-a607-94a2510c4a07
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 3%

---

# 定義事件鍵 {#concept_ond_hqt_52b}

金鑰是欄位或欄位組合是事件有效負載資料的一部分，且將允許系統識別與事件相關聯的人員。 金鑰可以是Experience CloudID、CRM ID或電子郵件地址。

如果您打算利用儲存在即時客戶配置檔案資料庫中的資料，則必須選擇[即時客戶配置檔案服務](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)中定義為配置檔案標識的資訊作為事件鍵。

它可讓系統執行事件與個人設定檔之間的調解。 如果選擇具有主要身份的架構，則預填&#x200B;**[!UICONTROL Key]**&#x200B;和&#x200B;**[!UICONTROL Namespace]**&#x200B;欄位。 如果沒有定義標識，則選擇&#x200B;_identityMap > id_&#x200B;作為主鍵。 然後，您必須選取命名空間，並使用&#x200B;_identityMap > id_&#x200B;預先填入索引鍵（在&#x200B;**[!UICONTROL Namespace]**&#x200B;欄位下方）。

選取欄位時，會標籤主要身分欄位。

![](../assets/primary-identity.png)

如果您需要使用不同的金鑰（例如CRM ID或電子郵件地址），則需要手動新增金鑰：

1. 按一下&#x200B;**[!UICONTROL Key]**&#x200B;欄位內或鉛筆圖示。

   ![](../assets/journey16.png)

1. 在有效負載欄位清單中選取作為索引鍵的欄位。 您也可以切換至進階運算式編輯器，以建立更複雜的索引鍵（例如，事件的兩個欄位串連）。 請參閱下文的本節。

   ![](../assets/journey20.png)

收到事件時，索引鍵的值可讓系統識別與事件相關聯的人員。 與命名空間相關聯（請參閱[此頁面](../event/selecting-the-namespace.md)），索引鍵可用於在Adobe Experience Platform上執行查詢。 請參閱[此頁面](../building-journeys/about-orchestration-activities.md)。金鑰也可用來檢查人員是否在歷程中。 事實上，一個人不可能在同一個旅程中處於兩個不同的位置。 因此，系統不允許相同的索引鍵（例如CRMID=3224）位於相同歷程中的不同位置。

如果要執行其他操作，您也可以訪問高級表達式函式(**[!UICONTROL Advanced mode]**)。 這些函式可讓您操控用於執行特定查詢的值，例如更改格式、執行欄位串連，而僅考慮欄位的一部分（例如10個前字元）。 請參閱[此頁面](../expression/expressionadvanced.md)。
