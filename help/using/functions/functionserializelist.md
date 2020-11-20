---
product: adobe campaign
solution: Journey Orchestration
title: serializeList
description: 瞭解函式serializeList
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 15%

---


# serializeList {#serializeList}

將第一個參數中給定的清單（任何類型）轉換為字串。 第二個參數代表要使用的分隔符號。 第三個參數是布林值，指出運算式的每個元素是否應包含引號。

## 類別

清單

## 函式語法

`serializeList(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| String | String |
| 布林值 | 布林值 |
| DateTimeOnly | DateTimeOnly |
| 清單 | listString |
| 清單 | listBoolean |
| 清單 | listPoint |
| 清單 | listDecimal |
| 清單 | listDuration |
| 清單 | listDateTime |
| 清單 | listDateTimeOnly |

## 簽名和傳回的類型

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

`serializeList(<listPoint>,<string>,<boolean>)`

傳回字串。

## 範例

`serializeList(["Hello","World"], " ", false)`

返回&quot;Hello World&quot;。

`serializeList(["Hello", "World"], ",", true)`

傳回&quot;Hello&quot;、&quot;World&quot;&quot;。
