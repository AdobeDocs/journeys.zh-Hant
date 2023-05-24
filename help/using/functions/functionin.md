---
product: adobe campaign
title: 在
description: 瞭解中的函式
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 6a19ae25-99c9-47f9-8417-c3d247dbbe3f
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 19%

---

# 在  {#in}

檢查清單中是否有第一個參數值。 檢查通過每個參數值上的Equal來執行。 如果找到參數值，則返回true，否則返回false。

類型 `<expression>` 必須與清單項匹配。 清單中項的類型（作為提醒）必須相互匹配。

## 類別

清單

## 函式語法

`in(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 字串 | 字串 |
| 布林值 | 布林值 |
| 整數 | 整數 |
| 十進位 | 十進位 |
| 持續時間 | 持續時間 |
| 日期時間 | 日期時間 |
| 僅日期時間 | 僅日期時間 |
| 清單 | 清單字串 |
| 清單 | list布爾 |
| 清單 | listInteger |
| 清單 | 清單十進位 |
| 清單 | listDuration（持續時間） |
| 清單 | 清單日期時間 |
| 清單 | listDateTimeOnly |
| 清單 | listDateOnly |

## 簽名和返回的類型

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<dateOnly>,<listDateOnly>)`

`in(<duration>,<listDuration>)`

返回布爾值。

## 範例

`in(4,[4,5,3,4])`

返回true。

`in(8,[4,5,3,4])`

返回false。

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`
