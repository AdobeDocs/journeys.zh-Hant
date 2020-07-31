---
title: 建立歷程
description: '瞭解如何建立進階的使用案例歷程 '
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
source-git-commit: 771b2b35e0aba412e4eb9e12a5d57de3d4c7068c
workflow-type: tm+mt
source-wordcount: '839'
ht-degree: 0%

---


# 建立歷程 {#concept_owm_kdy_w2b}

商 **業使用者** ，現在可以建立歷程。 我們的旅程將包括下列活動：

* 兩項 **[!UICONTROL Event]** 活動： &quot;LobbyBeacon&quot;和&quot;RestaurantBeacon&quot;
* 兩個活 **[!UICONTROL Condition]** 動
* 3個 **[!UICONTROL Push]** 活動和1 **[!UICONTROL Email]** 個活動（使用Adobe Campaign Standard）
* 活 **[!UICONTROL Wait]** 動
* 四個活 **[!UICONTROL End]** 動

>[!NOTE]
>
>只有在 **[!UICONTROL Push]** 您有 **[!UICONTROL Email]** Adobe Campaign Standard時，浮動視窗才能使用和活動。

如需如何建立歷程的詳細資訊，請參閱 [](../building-journeys/journey.md)。

## 第一步{#section_ntb_ws1_ffb}

1. 在頂端功能表中，按一下 **[!UICONTROL Home]** 標籤並 **[!UICONTROL Create]** 建立新的歷程。

   ![](../assets/journey31.png)

1. 在右側顯示的設定窗格中編輯歷程的屬性。 新增名稱，並將其設為12月1日至31日的1個月。

   ![](../assets/journeyuc2_12.png)

1. 從浮動視窗拖放「LobbyBeacon」事件至畫布，開始設計您的旅程。 您也可以連按兩下浮動視窗中的事件，將它新增至畫布。

   ![](../assets/journeyuc2_13.png)

1. 現在，我們新增一個條件來檢查此人在過去24小時內是否未被聯繫，並檢查他是否為忠誠會員。 將條件活動拖放至您的歷程中。

   ![](../assets/journeyuc2_14.png)

1. 選擇類 **[!UICONTROL Data Source Condition]** 型，然後在欄位中按一 **[!UICONTROL Expression]** 下。 您也可以定義條件標籤，該標籤將顯示在畫布的箭頭上。 在我們的範例中，我們將「條件1」取代為「忠誠會員」。

   ![](../assets/journeyuc2_15.png)

1. 按一 **[!UICONTROL Advanced mode]** 下並根據Adobe Experience Platform資料來源提供的「timestamp」和「directMarketing.sends.value」欄位，定義下列條件。 表達式的語法為：

   ```
   count(#{ExperiencePlatformDataSource.MarltonExperience.experienceevent.all(
       currentDataPackField.directMarketing.sends.value > 0 and
       currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
   and
       #{ExperiencePlatformDataSource.MarltonProfiles.Profile._customer.marlton.loyaltyMember}
   ```

   ![](../assets/journeyuc2_30.png)

1. 按一 **[!UICONTROL Add a path]** 下按鈕，為過去24小時內尚未連絡且非忠誠會員的客戶建立第二個路徑。 將路徑命名為「非忠誠度成員」。 表達式的語法為：

   ```
   count(#{ExperiencePlatformDataSource.MarltonExperience.experienceevent.all(
       currentDataPackField.directMarketing.sends.value > 0 and
       currentDataPackField.timestamp > nowWithDelta(-1, "days").timestamp}) == 0
   and not
       #{ExperiencePlatformDataSource.MarltonProfiles.Profile._customer.marlton.loyaltyMember}
   ```

   >[!NOTE]
   >
   >在運算式的第二部分中，「描述檔」是選用的。

1. 我們需要選擇一個命名空間。 基於架構屬性預選命名空間。 您可以保持預選。 有關名稱空間的詳細資訊，請參見 [](../event/selecting-the-namespace.md)。

在我們的使用案例中，我們只想對這兩種情況做出反應，所以我們不要勾選方塊 **[!UICONTROL Show path for other cases than the one(s) above]**。

在您的條件之後會建立兩個路徑：

* _過去24小時內未與客戶聯絡且是忠誠會員的客戶。_
* _過去24小時未與客戶聯絡，且不是忠誠會員的客戶。_

![](../assets/journeyuc2_16.png)

## 第一個路徑： 客戶是忠誠會員 {#section_otb_ws1_ffb}

1. 在第一個路徑中，我們新增條件來檢查他是否有保留。 將條件活動拖放至您的歷程中。

   ![](../assets/journeyuc2_17.png)

1. 選擇類 **[!UICONTROL Data Source Condition]** 型，並根據從保留系統檢索到的保留狀態資訊定義條件：

   ```
   #{MarltonReservation.MarltonFieldGroup.reservation} == true
   ```

   ![](../assets/journeyuc2_18.png)

1. 當您從外部資料來源選取欄位時，畫面的右側會顯示設定外部資料來源時所定義的參數清單(請參 [](../usecase/configuring-the-data-sources.md)閱)。 按一下參數名稱並定義保留系統索引鍵(Experience Cloud ID)的值，在我們的範例中：

   ```
   @{LobbyBeacon.endUserIDs._experience.mcid.id}
   ```

   ![](../assets/journeyuc2_19.png)

1. 由於我們也想對沒有預約的客戶作出反應，因此我們需要勾選方塊 **[!UICONTROL Show path for other cases than the one(s) above]**。

   ![](../assets/journeyuc2_20.png)

   會建立兩個路徑：

   * _已預訂房間的客戶_
   * _未訂房的客戶。_

   ![](../assets/journeyuc2_21.png)

1. 在第一個路徑（已預訂房間）中，拖 **[!UICONTROL Push]** 放活動，選擇您的行動應用程式和「歡迎」範本。

   ![](../assets/journeyuc2_22.png)

1. 定義系 **[!UICONTROL Target]** 統傳送推播所需的欄位。

   * **[!UICONTROL Push platform]**: 選擇平台： **[!UICONTROL Apple Push Notification Server]** (Apple)或 **[!UICONTROL Firebase Cloud Messaging]** (Android)。
   * **[!UICONTROL Registration token]**: 使用進階模式新增下列運算式（根據已設定的事件）:

      ```
      @{LobbyBeacon._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
      ```

1. 定義推播通知個人化欄位。 在我們的例子中： 名字和姓氏。

1. 新增「RestaurantBeacon」事件。

   ![](../assets/journeyuc2_23.png)

1. 新增活 **[!UICONTROL Push]** 動，選取「餐費折扣」範本並定義 **[!UICONTROL Address]** 和欄 **[!UICONTROL Personalization]** 位。 新增活 **[!UICONTROL End]** 動。

   ![](../assets/journeyuc2_24.png)

1. 我們只想在歡迎推播後6小時內進入餐廳時，傳送餐點折扣推播通知。 為此，我們需要使用等待活動。 將游標置於歡迎推播活動上，然後按一下&quot;+&quot;符號。 在新路徑中，新增等待活動並定義6小時的持續時間。 將選擇第一個符合資格的活動。 如果在歡迎推播後不到6小時收到餐廳事件，則會傳送推播活動。 如果未在接下來的6小時內收到餐廳事件，則選擇等待。 在等待活 **[!UICONTROL End]** 動之後放置活動。

   ![](../assets/journeyuc2_31.png)

1. 在遵循訂房條件的第二個路徑中（未預訂房間），添加活 **[!UICONTROL Push]** 動並選擇「房費」模板。 新增活 **[!UICONTROL End]** 動。

   ![](../assets/journeyuc2_25.png)

## 第二條路徑： 客戶不是忠誠會員{#section_ptb_ws1_ffb}

1. 在遵循第一個條件（客戶不是忠誠度會員）的第二個路徑中，新增活 **[!UICONTROL Email]** 動並選取「忠誠度會籍」範本。

   ![](../assets/journeyuc2_26.png)

1. 在欄位 **[!UICONTROL Address]** 中，選取資料來源的電子郵件地址。

   ![](../assets/journeyuc2_27.png)

1. 從資料來源定義名字和姓氏個人化欄位。

   ![](../assets/journeyuc2_28.png)

1. 新增活 **[!UICONTROL End]** 動。

按一下切 **[!UICONTROL Test]** 換並測試您的旅程。 如果有任何錯誤，請停用測試模式、修改您的歷程並再次測試。 有關測試模式的詳細資訊，請參閱 [](../building-journeys/testing-the-journey.md)。

![](../assets/journeyuc2_32bis.png)

當測試結果確定時，您可以從右上角的下拉式選單發佈您的旅程。

![](../assets/journeyuc2_32.png)
