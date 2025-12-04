---
product: adobe campaign
title: nowWithDelta
description: 瞭解函式nowWithDelta
feature: Journeys
role: Developer
level: Experienced
exl-id: f23f729b-7edb-4efc-a7ea-904314a7b2e1
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 7%

---

# nowWithDelta {#nowWithDelta}

傳回包含位移的目前日期時間。 如果指定了時區識別碼，則會套用時區位移。 如需資料型別的詳細資訊，請參閱[此頁面](../expression/data-types.md)。

## 類別

日期

## 函式語法

`nowWithDelta(<parameters>)`

## 參數

| 參數 | 說明 |
|--- |--- |
| delta | 正或負整數值 |
| 日期部分 | 年、月、日、小時、分鐘或秒做為字串 |
| 時區id | 時區值的字串表示法。 如需詳細資訊，請參閱[資料型別](../expression/data-types.md)。 時區ID必須是字串常數。 它不能是欄位參考或運算式。 |

## 簽章與傳回型別

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

傳回日期時間。

## 範例

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

傳回2小時前的dateTime。
