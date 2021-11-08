---
product: adobe campaign
title: matchRegExp
description: 了解函式matchRegExp
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 12%

---

# matchRegExp {#matchRegExp}

如果第一個參數中的字串符合第二個參數中的規則運算式，則傳回true。 如需詳細資訊，請參閱 [本頁](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

## 類別

字串

## 函式語法

`matchRegExp(<parameters>)`

## 參數

| 參數 | 類型 |
|--- |--- |
| 字串 | 字串 |
| regexp | 字串 |

## 簽名和返回類型

`matchRegExp(<string>,<string>)`

傳回布林值。

## 範例

`matchRegExp("Hello World", "Hello\s+World")`

傳回true。

說明：

在此，您可以檢查字串是否滿足規則運算式（java語法）:以&quot;Hello&quot;開頭，然後是任何類型的字串，結尾是&quot;World&quot;。
