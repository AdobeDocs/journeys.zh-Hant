---
product: adobe campaign
title: 定義事件鍵
description: 瞭解如何定義事件索引鍵
feature: Journeys
role: User
level: Intermediate
exl-id: 79bcf562-f971-42f1-a607-94a2510c4a07
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 5%

---

# 定義事件鍵 {#concept_ond_hqt_52b}

索引鍵是欄位或欄位組合是事件裝載資料的一部分，可讓系統識別與事件相關聯的人員。 例如，索引鍵可以是Experience CloudID、CRM ID或電子郵件地址。

如果您打算運用儲存在「即時客戶個人檔案」資料庫中的資料，您必須選取您定義為 [即時客戶個人檔案服務](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant).

這可讓系統在事件和個人設定檔之間執行調解。 如果您選取具有主要身分的綱要，則 **[!UICONTROL Key]** 和 **[!UICONTROL Namespace]** 欄位會預先填寫。 如果沒有定義身分，我們會選取 _identityMap > id_ 作為主索引鍵。 接著，您必須選取名稱空間，系統便會預先填入金鑰(位於 **[!UICONTROL Namespace]** 欄位)，使用 _identityMap > id_.

選取欄位時，會標籤主要身分欄位。

![](../assets/primary-identity.png)

如果您需要使用不同的金鑰，例如CRM ID或電子郵件地址，您需要手動新增：

1. 按一下 **[!UICONTROL Key]** 欄位或鉛筆圖示上。

   ![](../assets/journey16.png)

1. 選取在裝載欄位清單中選為索引鍵的欄位。 您也可以切換至進階運算式編輯器，以建立更複雜的索引鍵（例如，兩個事件欄位的串連）。 請參閱下文，在本節中。

   ![](../assets/journey20.png)

收到事件時，機碼的值將可讓系統識別與事件相關聯的人員。 與名稱空間相關聯(請參閱 [此頁面](../event/selecting-the-namespace.md))，則金鑰可用來在Adobe Experience Platform上執行查詢。 請參閱[此頁面](../building-journeys/about-orchestration-activities.md)。金鑰也可用來檢查個人是否在歷程中。 事實上，一個人在同一歷程中不能位於兩個不同的位置。 因此，系統不允許相同的金鑰（例如金鑰CRMID=3224）位於相同歷程中的不同位置。

您也可以存取進階運算式函式(**[!UICONTROL Advanced mode]**)。 這些函式可讓您控制用於執行特定查詢的值，例如變更格式、執行欄位串連，僅考慮欄位的一部分（例如10個第一個字元）。 請參閱[此頁面](../expression/expressionadvanced.md)。
