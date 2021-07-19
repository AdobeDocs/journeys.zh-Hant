---
product: adobe campaign
title: nowWithDelta
description: 了解函式nowWithDelta
feature: 歷程
role: Data Engineer
level: Experienced
exl-id: f23f729b-7edb-4efc-a7ea-904314a7b2e1
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 8%

---

# nowWithDelta {#nowWithDelta}

返回包含偏移的當前日期時間。 如果指定了時區ID，則會套用時區偏移。 有關資料類型的詳細資訊，請參閱[本頁](../expression/data-types.md)。

## 類別

Date

## 函式語法

`nowWithDelta(<parameters>)`

## 參數

| 參數 | 說明 |
|--- |--- |
| delta | 正整數或負整數值 |
| 日期部分 | 年、月、天、小時、分鐘或秒作為字串 |
| 時區id | 時區值的字串表示法。 如需詳細資訊，請參閱[資料類型](../expression/data-types.md)。 時區ID必須是字串常數。 它不能是欄位參考或運算式。 |

## 簽名和返回類型

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

傳回dateTime。

## 範例

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

傳回2小時前的dateTime。
