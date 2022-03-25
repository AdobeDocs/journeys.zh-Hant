---
product: adobe campaign
title: concat
description: 瞭解函式概念
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7a516705-2bbe-4b42-97fc-aeae11082002
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 27%

---

# 康 {#concat}

連接兩個字串參數或字串清單。

## 類別

字串

## 函式語法

`concat(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 清單 | 清單字串 |
| 字串 | 字串 |

## 簽名和返回的類型

`concat(<string>,<string>)`

`concat(<listString>)`

返回字串。

## 範例

`concat("Hello","World")`

返回&quot;HelloWorld&quot;。

`concat(["Hello"," ","World"])`

返回「Hello World」。
