---
product: adobe campaign
title: 關於事件
description: 了解事件
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 2115ab1d-1084-4429-8315-0357c8525c47
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 48%

---

# 一般原則 {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="關於事件"
>abstract="事件會連結至人員，它與人的行為或與人相關的事情有關。 這是 [!DNL Journey Orchestration] 在歷程中會監聽的事件，以便協調下一個最佳動作。"

事件會連結至人員，它與人的行為相關（例如，某人購買產品、造訪商店、離開網站等等）或是某人發生的事（例如，某人達到 10,000 點忠誠點數）。這是 [!DNL Journey Orchestration] 在歷程中會監聽的事件，以便協調下一個最佳動作。

此設定是&#x200B;**強制性**&#x200B;的，因為 [!DNL Journey Orchestration] 的設計旨在監聽事件，且一律會由&#x200B;**技術使用者**&#x200B;執行。

事件設定可讓您定義 [!DNL Journey Orchestration] 會接收以作為事件的資訊。您可以使用數個事件（在歷程的不同步驟中），而數個歷程則可以使用同一個事件。

如果您編輯草稿或即時歷程中使用的事件，則只能變更名稱和說明，或是新增有效負載欄位。我們對草稿或即時歷程版本有嚴格限制，以免中斷歷程。

您可以定義兩種事件：

* **規則基** 礎事件：此類型的事件不會產生eventID。使用簡單運算式編輯器，您只需定義一個規則，系統將使用該規則來識別將觸發您歷程的相關事件。 此規則可以根據事件裝載中可用的任何欄位，例如設定檔的位置或新增至設定檔購物車的項目數。

   >[!CAUTION]
   >
   >已為規則型事件定義上限規則。 此量度會將歷程可處理的合格事件數限制為指定組織(ORG)的每秒5000次。 它對應於Journey OrchestrationSLA。 請參閱此[page](https://helpx.adobe.com/legal/product-descriptions/journey-orchestration.html)。

* **系統生** 成事件：這些事件需要eventID。建立事件時，會自動產生此eventID欄位。 推送事件的系統不應產生ID，而應傳遞有效負載預覽中可用的ID。

若要了解如何建立事件，請參閱此[page](../event/about-creating.md)。
