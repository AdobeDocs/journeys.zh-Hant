---
product: adobe campaign
solution: Journey Orchestration
title: matchRegExp
description: 瞭解函式matchRegExp
feature: 旅程
role: 資料工程師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 5%

---


# matchRegExp {#matchRegExp}

如果第一個參數中的字串與第二個參數中的規則運算式相符，則傳回true。 如需詳細資訊，請參閱[本頁](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html)。

## 類別

String

## 函式語法

`matchRegExp(<parameters>)`

## 參數

| 參數 | 類型 |
|--- |--- |
| 字串 | 字串 |
| regexp | 字串 |

## 簽名和傳回的類型

`matchRegExp(<string>,<string>)`

傳回true。

## 範例

`matchRegExp("Hello World", "Hello\s+World")`

傳回true。

說明：

在這裡，您可檢查字串是否滿足規則運算式（java語法）:開頭為&quot;Hello&quot;，然後是任何字串，結尾為&quot;World&quot;。
