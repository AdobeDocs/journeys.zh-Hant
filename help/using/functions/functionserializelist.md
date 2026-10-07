---
product: adobe campaign
title: serializeList
description: 瞭解函式serializeList
feature: Journeys
role: Developer
level: Experienced
exl-id: 84912d38-32ee-4cfe-8cb4-bad12f9c52af
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 22%
---
# serializeList {#serializeList}

將第一個引數中指定的清單（任何型別）轉換為字串。 第二個引數代表要使用的分隔符號。 第三個引數是布林值，指出運算式的每個元素是否應該包含引號。

## 類別

清單

## 函式語法

`serializeList(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 字串 | 字串 |
| 布林值 | 布林值 |
| DateTimeOnly | DateTimeOnly |
| 清單 | listString |
| 清單 | listBoolean |
| 清單 | listPoint |
| 清單 | listDecimal |
| 清單 | listDuration |
| 清單 | listDateTime |
| 清單 | listDateTimeOnly |
| 清單 | listDateOnly |

## 簽章與傳回的型別

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDateOnly>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

`serializeList(<listPoint>,<string>,<boolean>)`

傳回字串。

## 範例

`serializeList(["Hello","World"], " ", false)`

傳回「Hello World」。

`serializeList(["Hello", "World"], ",", true)`

傳回&quot;Hello&quot;、&quot;World&quot;。
