---
product: adobe campaign
title: 定義事件鍵
description: 瞭解如何定義事件密鑰
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

關鍵字是欄位或欄位組合是事件負載資料的一部分，它將允許系統標識與事件關聯的人員。 密鑰可以是Experience CloudID、CRM ID或電子郵件地址。

如果您計畫利用儲存在Real-time Customer Profile資料庫中的資料，則必須選擇在中定義為配置檔案標識的資訊作為事件鍵 [即時客戶配置檔案服務](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant)。

它將允許系統執行事件與個人配置檔案之間的協調。 如果選擇具有主標識的架構，則 **[!UICONTROL Key]** 和 **[!UICONTROL Namespace]** 欄位已預填充。 如果沒有定義標識，我們將選擇 _identityMap > id_ 鍵。 然後，必須選擇一個命名空間，並且該鍵將預填充(位於 **[!UICONTROL Namespace]** 欄位使用 _identityMap > id_。

選擇欄位時，將標籤主標識欄位。

![](../assets/primary-identity.png)

如果您需要使用其他密鑰，例如CRM ID或電子郵件地址，則需要手動添加：

1. 在 **[!UICONTROL Key]** 表徵圖。

   ![](../assets/journey16.png)

1. 在有效負載欄位清單中選擇作為鍵的欄位。 您還可以切換到高級表達式編輯器來建立更複雜的鍵（例如，兩個事件欄位的串聯）。 請參閱下面的本節。

   ![](../assets/journey20.png)

當收到事件時，該鍵的值將允許系統標識與該事件關聯的人員。 與命名空間關聯(請參見 [此頁](../event/selecting-the-namespace.md))，該鍵可用於在Adobe Experience Platform上執行查詢。 請參閱[此頁面](../building-journeys/about-orchestration-activities.md)。鑰匙還用於檢查人是否在旅途中。 事實上，一個人不可能在同一旅程中處於兩個不同的位置。 因此，系統不允許相同的密鑰（例如，密鑰CRMID=3224）在相同行程的不同位置處。

您還可以訪問高級表達式函式(**[!UICONTROL Advanced mode]**)。 通過這些函式，您可以處理用於執行特定查詢的值，例如更改格式、執行欄位連接，只考慮欄位的一部分（例如10個首字元）。 請參閱[此頁面](../expression/expressionadvanced.md)。
