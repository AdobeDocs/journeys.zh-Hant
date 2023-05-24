---
product: adobe campaign
title: toString
description: 瞭解函式toString
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 942e7a44-1cb1-4c99-abd6-e0b045c42c80
source-git-commit: c7730ecac062719e5e5adfd465d1cedb59b3eaf1
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 9%

---

# toString {#toString}

根據參數值的類型將參數值轉換為字串值。 有關資料類型的詳細資訊，請參閱 [此頁](../expression/data-types.md)。

## 類別

轉換

## 函式語法

`toString(<parameter>)`

## 參數

| 參數 | 說明 |
|--- |--- |
| 日期時間 | 轉換UTC日期格式的日期 |
| 日期僅時間 | 轉換UTC日期格式的日期 |
| 持續時間 | 轉換為字串形式的相應毫秒數 |
| 整數 | 轉換為值的字串表示形式（1變為&quot;1&quot;） |
| 小數 | 轉換為值的字串表示形式（1.5變為&quot;1.5&quot;） |
| 布林值 | 如果為true，則將布爾值轉換為「true」；如果為false，則將布爾值轉換為「false」 |

## 簽名和返回的類型

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

返回字串。

## 範例

`toString(4)`

返回&quot;4&quot;。
