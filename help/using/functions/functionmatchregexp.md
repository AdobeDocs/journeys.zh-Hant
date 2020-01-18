---
title: matchRegExp
description: 瞭解函式matchRegExp
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

---


# matchRegExp {#matchRegExp}

如果第一個參數中的字串與第二個參數中的規則運算式相符，則傳回true。 如需詳細資訊，請參 [閱本頁](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html)。

## 類別

字串

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
