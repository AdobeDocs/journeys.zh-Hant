---
product: adobe campaign
title: inSegment
description: 瞭解Segment中的函式
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
source-git-commit: e56e6f5dcb8a4680851858355ac18a70bd832b73
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 6%

---

# 在段中 {#inSegment}

檢查個人是否屬於給定段。

>[!NOTE]
>
>可檢索多達100個段。

段名稱必須是字串常數。 它不能是欄位引用或表達式。

段定義於 [Adobe Experience Platform](https://platform.adobe.com/segment/overview)。 表達式編輯器提供自動完成的段清單。

段可以有三種狀態：

* 現有：實體繼續在該分部。
* 實現：實體正在輸入段。
* 已退出：實體正在退出段。

只有那些 **已實現** 和 **現有** 段參與狀態將被視為段的成員。 有關如何評估段的詳細資訊，請參閱 [分段服務文檔](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results)。

`IF inSegment('segmentName') == true` 表示您具有已輸入/現有狀態的segmentship。

`ELSE inSegment('segmentName') == false` 表示您具有退出狀態的segmembers。

## 類別

Adobe Experience Platform

## 函式語法

`inSegment(<parameter>)`

## 參數

| 參數 | 說明 | 類型 |
|--- |--- |--- |
| 區段 | 段名稱 | `<string>` |

## 簽名和返回的類型

`inSegment(<string>)`

返回布爾值。

## 範例

`inSegment("men over 50")`

說明：

函式將返回 **[!UICONTROL true]** 如果旅程實例中的個人是Adobe Experience Platform段&quot;50歲以上的男性&quot;的一部分， **[!UICONTROL false]** 否則。
