---
product: adobe campaign
solution: Journey Orchestration
title: matchRegExp
description: 瞭解函式matchRegExp
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 4%

---


# matchRegExp {#matchRegExp}

如果第一個參數中的字串與第二個參數中的規則運算式相符，則傳回true。 如需詳細資訊，請參 [閱本頁](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html)。

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
