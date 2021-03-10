---
product: adobe campaign
solution: Journey Orchestration
title: nowWithDelta
description: 瞭解函式nowWithDelta
feature: 旅程
role: 資料工程師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 5%

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
