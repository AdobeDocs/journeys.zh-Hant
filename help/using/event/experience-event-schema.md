---
title: '關於歷程協調事件的ExperienceEvent結構描述 '
description: '瞭解歷程協調事件的ExperienceEvent架構 '
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 0%

---



# 關於事件的ExperienceEvent結 [!DNL Journey Orchestration] 構

[!DNL Journey Orchestration] 事件是透過串流擷取傳送至Adobe Experience Platform的XDM Experience Events。

因此，設定事件的重要先決條件是您熟悉 [!DNL Journey Orchestration] Adobe Experience Platform的「體驗資料模型」（或XDM），以及如何組成XDM體驗事件結構，以及如何將XDM格式的資料串流至Adobe Experience Platform。

## 事件的架構需 [!DNL Journey Orchestration] 求

設定事件的第一步是確 [!DNL Journey Orchestration] 保您已定義XDM架構來代表事件，並建立資料集來記錄Adobe Experience Platform上的事件例項。 您並不需要為事件建立資料集，但是將事件傳送至特定資料集可讓您維護使用者的事件歷史記錄，以供日後參考和分析，因此這永遠是個好主意。 如果您尚未擁有適合事件的架構和資料集，這兩項工作都可在Adobe Experience Platform網頁介面中完成。

![](../assets/schema1.png)

將用於事件的任何XDM [!DNL Journey Orchestration] 架構都應滿足以下要求：

* 架構必須是XDM ExperienceEvent類別。

![](../assets/schema2.png)

* 架構必須包含Orchestration eventID mixin。 [!DNL Journey Orchestration] 使用此欄位來識別歷程中使用的事件。

![](../assets/schema3.png)

* 宣告識別欄位以識別事件的主體。 如果未指定任何身分，則可使用身份映射。 不建議使用。

![](../assets/schema4.png)

* 如果您希望此資料在稍後的歷程中可供查閱，請標籤描述檔和資料集。

![](../assets/schema5.png)

![](../assets/schema6.png)

* 您可自由地加入資料欄位，以擷取您想要與事件一起包含的任何其他上下文資料，例如有關使用者、事件產生裝置、位置或與事件相關的任何其他有意義情況的資訊。

![](../assets/schema7.png)

![](../assets/schema8.png)