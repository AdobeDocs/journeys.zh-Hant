---
title: nowWithDelta
description: 瞭解函式nowWithDelta
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
source-git-commit: 239efa9592b011c70e2fc331df8f33820301253d
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 4%

---


# nowWithDelta {#nowWithDelta}

返回包含偏移的當前日期時間。 如果指定時區ID，則會套用時區偏移。 有關資料類型的詳細資訊，請參閱 [](../expression/data-types.md)。

## 類別

日期

## 函式語法

`nowWithDelta(<parameters>)`

## 參數

| 參數 | 說明 |
|--- |--- |
| δ | 正整數值 |
| 日期部分 | 年、月、日、小時、分或秒作為字串 |
| 時區ID | 字串表示時區值。 有關詳細資訊，請參 [](../expression/data-types.md)閱。 時區ID必須是字串常數。 它不能是欄位引用或表達式。 |

## 簽名和傳回類型

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

傳回dateTime。

## 範例

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

傳回2小時前的dateTime。
