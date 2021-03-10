---
product: adobe campaign
solution: Journey Orchestration
title: 定義事件鍵
description: 瞭解如何定義事件索引鍵
feature: 旅程
role: 業務從業人員
level: 中級
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 5%

---


# 定義事件鍵 {#concept_ond_hqt_52b}

關鍵字是欄位或欄位組合是事件裝載資料的一部分，可讓系統識別與事件相關聯的人員。 金鑰可以是Experience CloudID、CRM ID或電子郵件地址。

如果您打算利用儲存在即時客戶配置檔案資料庫中的資料，則必須選擇在[即時客戶配置檔案服務](https://docs.adobe.com/content/help/zh-Hant/experience-platform/profile/home.html)中定義為配置檔案標識的資訊作為事件鍵。

它可讓系統執行事件與個人設定檔之間的協調。 如果選擇具有主標識的方案，則預填充&#x200B;**[!UICONTROL Key]**&#x200B;和&#x200B;**[!UICONTROL Namespace]**&#x200B;欄位。 如果未定義身份，我們將選擇&#x200B;_identityMap > id_&#x200B;作為主鍵。 然後，您必須選擇命名空間，然後使用&#x200B;_identityMap > id_&#x200B;預先填入索引鍵（位於&#x200B;**[!UICONTROL Namespace]**&#x200B;欄位下方）。

選擇欄位時，標籤主標識欄位。

![](../assets/primary-identity.png)

如果您需要使用不同的金鑰，例如CRM ID或電子郵件地址，則需手動新增：

1. 在&#x200B;**[!UICONTROL Key]**&#x200B;欄位內按一下，或在鉛筆圖示上按一下。

   ![](../assets/journey16.png)

1. 在裝載欄位清單中選擇作為鍵的欄位。 您也可以切換至進階運算式編輯器，以建立更複雜的索引鍵（例如，事件的兩個欄位串連）。 請參閱以下章節。

   ![](../assets/journey20.png)

收到事件時，鍵值將允許系統識別與事件相關聯的人。 與命名空間相關聯（請參閱[本頁](../event/selecting-the-namespace.md)），該鍵可用於在Adobe Experience Platform上執行查詢。 請參閱[本頁](../building-journeys/about-orchestration-activities.md)。鑰匙也用來檢查一個人是否在旅程中。 事實上，一個人不可能在同一旅程的兩個不同地方。 因此，系統不允許相同的密鑰（例如，密鑰CRMID=3224）在同一行程的不同位置。

如果您想要執行其他操作，也可以訪問高級表達式函式(**[!UICONTROL Advanced mode]**)。 這些函式可讓您控制用於執行特定查詢的值，例如變更格式、執行欄位串連，只考慮欄位的一部分（例如10個前字元）。 請參閱[本頁](../expression/expressionadvanced.md)。
