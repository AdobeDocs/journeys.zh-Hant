---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: 瞭解inSegment的函式
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: a99ad6a589bcd1f3083eabbcac35dd5c0497093d
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 5%

---


# inSegment {#inSegment}

檢查個人是否屬於指定區段。

>[!NOTE]
>
>您最多可擷取100個區段。

區段名稱必須是字串常數。 它不能是欄位引用或表達式。

區段定義於[Adobe Experience Platform](https://platform.adobe.com/segment/overview)中。 運算式編輯器提供自動完成的區段清單。

>[!NOTE]
>
>只有具有&#x200B;**Remailed**&#x200B;和&#x200B;**Existing**&#x200B;區段參與狀態的個人才會被視為區段的成員。 如需如何評估區段的詳細資訊，請參閱[區段服務檔案](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results)。

## 類別

Adobe Experience Platform

## 函式語法

`inSegment(<parameter>)`

## 參數

| 參數 | 說明 | 類型 |
|--- |--- |--- |
| 區段 | 區段名稱 | `<string>` |

## 簽名和傳回的類型

`inSegment(<string>)`

傳回布林值。

## 範例

`inSegment("men over 50")`

說明：

如果歷程例項中的個人屬於名為&quot;men over 50&quot;的Adobe Experience Platform區段，則函式會傳回&#x200B;**[!UICONTROL true]**，否則會傳回&#x200B;**[!UICONTROL false]**。
