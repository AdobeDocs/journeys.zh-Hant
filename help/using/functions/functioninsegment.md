---
product: adobe campaign
title: inSegment
description: 了解inSegment的函式
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
source-git-commit: e56e6f5dcb8a4680851858355ac18a70bd832b73
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 6%

---

# inSegment {#inSegment}

檢查個別是否屬於指定區段。

>[!NOTE]
>
>您最多可擷取100個區段。

區段名稱必須是字串常數。 它不能是欄位參考或運算式。

區段是在[Adobe Experience Platform](https://platform.adobe.com/segment/overview)中定義。 運算式編輯器提供自動完成的區段清單。

區段可以有三種狀態：

* 現有：實體繼續在分部中。
* 已實現：實體正在輸入區段。
* 退出：entity正在退出區段。

只有具有&#x200B;**Remailed**&#x200B;和&#x200B;**Existing**&#x200B;區段參與狀態的個人才會被視為區段的成員。 如需如何評估區段的詳細資訊，請參閱[分段服務檔案](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results)。

`IF inSegment('segmentName') == true` 表示您有segmentMembership，且狀態為「已輸入/現有」。

`ELSE inSegment('segmentName') == false` 表示您擁有退出狀態的segmentMembersip。

## 類別

Adobe Experience Platform

## 函式語法

`inSegment(<parameter>)`

## 參數

| 參數 | 說明 | 類型 |
|--- |--- |--- |
| 區段 | 區段名稱 | `<string>` |

## 簽名和返回類型

`inSegment(<string>)`

傳回布林值。

## 範例

`inSegment("men over 50")`

說明：

如果歷程例項中的個人屬於名為「50歲以上的男性」的Adobe Experience Platform區段，則函式會傳回&#x200B;**[!UICONTROL true]**，否則會傳回&#x200B;**[!UICONTROL false]**。
