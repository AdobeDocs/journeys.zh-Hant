---
product: adobe campaign
title: journeyStep 事件識別欄位
description: journeyStep 事件識別欄位
feature: Journeys
role: User
level: Intermediate
exl-id: 9c0ff38f-51dd-40bd-8c19-d142b9c23308
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 12%

---

# journeyStep 事件識別欄位 {#sharing-identity-fields}


>[!CAUTION]
>
>**正在尋找Adobe Journey Optimizer**？ 如需Journey Optimizer檔案，請按一下[這裡](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/ajo-home){target="_blank"}。
>
>
>_本檔案參考已由Journey Optimizer取代的舊版Journey Orchestration資料。 如果您對Journey Orchestration或Journey Optimizer的存取權有任何疑問，請聯絡您的帳戶團隊。_


此Mixin專用於journeyStepEvent：此事件與歷程相關，且沒有identityMap，無法描述設定檔身分（如有）。

若為journeyStepEvent，我們還需要新增與身分相關的欄位：

## profileID

設定檔識別碼

型別：字串

## profileNamespace

設定檔識別碼名稱空間

型別：字串
