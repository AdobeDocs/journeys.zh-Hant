---
product: adobe campaign
title: 欄位群組
description: 瞭解欄位群組
feature: Journeys
role: User
level: Intermediate
exl-id: 6f7f2673-9080-4274-afa3-a0255798f78d
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 1%

---

# 欄位群組 {#concept_ntl_ypt_52b}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_


欄位群組是一組欄位，您可以從資料來源擷取並在歷程中使用。

## 定義欄位群組 {#section_dsz_kjd_fjb}

對於每個資料來源，您可以定義數個欄位群組。

例如，您可以使用電話號碼、電子郵件、名字和個人資料地址來建立欄位群組。 然後，您就可以在歷程中使用此資料來建立條件。 例如，您可以決定只有在設定檔的電話號碼非空白時才傳送簡訊。 如果空白，您可以傳送電子郵件。

即使自動新增預設名稱，我們仍建議您為欄位群組提供名稱。 事實上，[!DNL Journey Orchestration]中的其他使用者可以看到欄位群組名稱。 為欄位群組指定相關名稱是最佳做法。

當歷程中使用資料來源欄位時，系統會擷取為該欄位群組定義的所有欄位。 因此，最佳實務就是僅選取歷程所需的欄位。 這將減少歷程中的請求延遲，從而提高效能。 請注意，您稍後可輕鬆在欄位群組中新增更多欄位。

使用欄位群組的歷程次數會顯示在&#x200B;**[!UICONTROL Used in]**&#x200B;欄位中。 您可以按一下&#x200B;**[!UICONTROL View journeys]**&#x200B;按鈕，以顯示使用此欄位群組的歷程清單。

>[!NOTE]
>
>請注意，如果欄位群組沒有欄位，則運算式編輯器中不會顯示該欄位。

![](../assets/journey3bis.png)

## 欄位群組生命週期 {#section_abk_njd_fjb}

您可以從未用於任何草稿或即時歷程的欄位群組中新增或移除欄位。

您可以新增欄位，但無法從一個或多個草稿或即時歷程中使用的欄位群組中移除欄位。 這將避免中斷歷程。

若要從用於一或多個歷程的欄位群組中刪除欄位，請按照以下步驟操作。 讓我們以名為「欄位群組A」的欄位群組為例。

1. 在欄位群組清單中，將游標置於「欄位群組A」上，然後按一下右側的&#x200B;**[!UICONTROL Duplicate]**&#x200B;圖示。 例如，將複製的欄位群組命名為「欄位群組B」。
1. 在「欄位群組B」中，移除您不再想要的欄位。
1. 在「欄位群組A」中，檢查此欄位群組的使用位置。 此資訊會顯示在&#x200B;**[!UICONTROL Used in]**&#x200B;欄位中。
1. 開啟所有使用「欄位群組A」的歷程。
1. 為每個歷程建立新版本。 使用「欄位群組A」編輯所有活動並選取「欄位群組B」。
1. 停止使用「欄位群組A」的舊版歷程。 然後，您應該沒有使用「欄位群組A」的歷程。
1. 移除「欄位群組A」，因為它已不再使用。
