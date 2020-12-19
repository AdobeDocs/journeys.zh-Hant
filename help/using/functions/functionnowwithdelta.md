---
product: adobe campaign
solution: Journey Orchestration
title: nowWithDelta
description: 瞭解函式nowWithDelta
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 4%

---


# nowWithDelta {#nowWithDelta}

返回包含偏移的當前日期時間。 如果指定時區ID，則會套用時區偏移。 有關資料類型的詳細資訊，請參閱[此頁](../expression/data-types.md)。

## 類別

日期

## 函式語法

`nowWithDelta(<parameters>)`

## 參數

| 參數 | 說明 |
|--- |--- |
| δ | 正整數值 |
| 日期部分 | 年、月、日、小時、分或秒作為字串 |
| 時區ID | 字串表示時區值。 如需詳細資訊，請參閱[資料類型](../expression/data-types.md)。 時區ID必須是字串常數。 它不能是欄位引用或表達式。 |

## 簽名和傳回類型

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

傳回dateTime。

## 範例

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

傳回2小時前的dateTime。
