---
title: 存取管理
description: 進一步瞭解存取管理
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27

---


# 存取管理{#concept_rfj_wpt_52b}

## 關於存取管理 {#about-access-management}

產品設定檔會指派給一組使用者，這些使用者在您的組織中擁有相同的權限。

在「管理控制台」中，您可以指派下列其中一個現成可用的產品設定檔給您的使用者：

* **[!UICONTROL Limited Access User]**:具有歷程和報告唯讀存取權的使用者。 此產品設定檔包含下列權限：
   * 閱讀歷程
   * 閱讀報告

* **[!UICONTROL Administrators]**:使用者可存取管理功能表，並可管理歷程、事件和報表。 此產品設定檔包含下列權限：
   * 管理和執行歷程
   * 管理事件、資料來源和動作
   * 管理報表
   >[!NOTE]
   >
   >**[!UICONTROL Administrators]**是唯一允許在Adobe Campaign standard中建立、編輯和發佈交易訊息（或訊息範本）的產品設定檔。 如果您使用Adobe Campaign standard在歷程中傳送訊息，就需要此產品設定檔。

* **[!UICONTROL Standard User]**:具有基本存取權的使用者，例如歷程管理。 此產品設定檔包含下列權限：
   * 管理和執行歷程
   * 管理報表

您可在這裡 [找到](../assets/do-not-localize/acs_rights_journeys.pdf) ，權限與Journey Orchestration不同功能之間的相容性。

## 指派產品設定檔 {#assigning-product-profile}

產品設定檔是在管理控制台中管理。 如需詳細資訊，請參閱「管理控 [制台」檔案](https://helpx.adobe.com/enterprise/managing/user-guide.html)。

要為用戶分配產品配置檔案以訪問Journey Orchestration:

1. 在管理控制台中，選取 **[!UICONTROL Journey orchestration]**。

   ![](../assets/user_management.png)

1. 選擇新使用者將連結至的產品設定檔。

   ![](../assets/user_management_2.png)

1. 按一下 **[!UICONTROL Add user]**.

   您也可以將新使用者新增至使用者群組，以微調共用權限集。 For more on this, refer to this [page](https://helpx.adobe.com/enterprise/using/user-groups.html).

   ![](../assets/user_management_3.png)

1. 輸入新使用者的電子郵件地址，然後按一下 **[!UICONTROL Save]**。

   ![](../assets/user_management_4.png)

然後，您的使用者應該會收到電子郵件，重新導向至您的Journey Orchestration實例。