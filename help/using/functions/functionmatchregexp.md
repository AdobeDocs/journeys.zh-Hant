---
product: adobe campaign
title: matchRegExp
description: 瞭解函式matchRegExp
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: a5d063784b278120b61f8d2641264baf40e34a90
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 18%

---

# matchRegExp {#matchRegExp}

如果第一個引數中的字串符合第二個引數中的規則運算式，則傳回true。 如需詳細資訊，請參閱 [此頁面](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

## 類別

字串

## 函式語法

`matchRegExp(<parameters>)`

## 參數

| 參數 | 類型 |
|--- |--- |
| 字串 | 字串 |
| regexp | 字串 |

## 簽章與傳回的型別

`matchRegExp(<string>,<string>)`

傳回布林值。

## 範例

`matchRegExp("username@adobe.com", "*adobe")`

傳回true。
