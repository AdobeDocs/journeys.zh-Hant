---
product: adobe campaign
title: '在 '
description: 了解中的函式
feature: 歷程
role: Data Engineer
level: Experienced
exl-id: 6a19ae25-99c9-47f9-8417-c3d247dbbe3f
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 17%

---

# 在  {#in}

檢查清單中是否有第一個引數值。 檢查是通過每個參數值的Equal來執行的。 若找到引數值，則傳回true，否則傳回false。

`<expression>`的類型必須與清單的項目相符。 清單項目的類型（作為提醒）必須彼此匹配。

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
| 小數 | 小數 |
| 持續時間 | 持續時間 |
| DateTime | DateTime |
| DateTimeOnly | DateTimeOnly |
| 清單 | listString |
| 清單 | listBoolean |
| 清單 | listInteger |
| 清單 | listDecimal |
| 清單 | listDuration |
| 清單 | listDateTime |
| 清單 | listDateTimeOnly |

## 簽名和返回類型

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<duration>,<listDuration>)`

傳回布林值。

## 範例

`in(4,[4,5,3,4])`

傳回true。

`in(8,[4,5,3,4])`

傳回false。

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`
