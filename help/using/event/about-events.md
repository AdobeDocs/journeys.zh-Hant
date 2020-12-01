---
product: adobe campaign
solution: Journey Orchestration
title: 關於事件
description: 瞭解活動
translation-type: tm+mt
source-git-commit: c66c09441f69e7026c60c37f87972e1e4ac9f7f8
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 54%

---


# 一般原則{#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="關於事件"
>abstract="事件會連結至人員，它與人的行為相關（例如，某人購買產品、造訪商店、離開網站等等）或是某人發生的事（例如，某人達到 10,000 點忠誠點數）。這是 [!DNL Journey Orchestration] 在歷程中會監聽的事件，以便協調下一個最佳動作。"

事件會連結至人員，它與人的行為相關（例如，某人購買產品、造訪商店、離開網站等等）或是某人發生的事（例如，某人達到 10,000 點忠誠點數）。這是 [!DNL Journey Orchestration] 在歷程中會監聽的事件，以便協調下一個最佳動作。

此設定是&#x200B;**強制性**&#x200B;的，因為 [!DNL Journey Orchestration] 的設計旨在監聽事件，且一律會由&#x200B;**技術使用者**&#x200B;執行。

事件設定可讓您定義 [!DNL Journey Orchestration] 會接收以作為事件的資訊。您可以使用數個事件（在歷程的不同步驟中），而數個歷程則可以使用同一個事件。

如果您編輯草稿或即時歷程中使用的事件，則只能變更名稱和說明，或是新增有效負載欄位。我們對草稿或即時歷程版本有嚴格限制，以免中斷歷程。

您可以定義兩種事件：

* **規則型事件** :此類型的事件不會產生eventID。 使用簡單運算式編輯器，您只需定義規則，系統將使用該規則來識別將觸發歷程的相關事件。 此規則可以根據事件裝載中可用的任何欄位，例如描述檔位置或新增至描述檔購物車的項目數。

   >[!CAUTION]
   >
   >會為規則型事件定義上限規則。 它可將歷程處理的合格事件數限制為每分鐘400k。 如需詳細資訊，請洽詢您的Alpha計畫聯絡點。 除了此限制規則外，在歷程層級定義5000個事件的秒數限制。

* **系統產生的事件** :這些事件需要eventID。 建立事件時會自動產生此eventID欄位。 推送事件的系統不應產生ID，而應傳遞裝載預覽中可用的ID。

要瞭解如何建立事件，請參閱本 [頁](../event/about-creating.md)。

