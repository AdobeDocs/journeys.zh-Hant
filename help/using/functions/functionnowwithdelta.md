---
product: adobe campaign
title: nowWithDelta
description: 瞭解函式nowWithDelta
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: f23f729b-7edb-4efc-a7ea-904314a7b2e1
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 7%

---

# nowWithDelta {#nowWithDelta}

返回當前日期時間（包括偏移）。 如果指定了時區ID，將應用時區偏移。 有關資料類型的詳細資訊，請參閱 [此頁](../expression/data-types.md)。

## 類別

日期

## 函式語法

`nowWithDelta(<parameters>)`

## 參數

| 參數 | 說明 |
|--- |--- |
| 三角 | 正整數 |
| 日期部分 | 年、月、天、小時、分或秒（字串） |
| 時區ID | 時區值的字串表示法。 有關詳細資訊，請參見 [資料類型](../expression/data-types.md)。 時區ID必須是字串常數。 它不能是欄位引用或表達式。 |

## 簽名和返回的類型

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

返回dateTime。

## 範例

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

返回2小時前的dateTime。
