---
product: adobe campaign
title: startWithIgnoreCase
description: 瞭解函式startWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 0ef098d8-b56c-4509-bbbd-2688ecc547bf
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 25%

---

# startWithIgnoreCase {#startWithIgnoreCase}

如果第二個引數是第一個引數的前置詞，則傳回true，而不考慮大小寫。

## 類別

字串

## 函式語法

`startWithIgnoreCase(<parameters>)`

## 參數

| 參數 | 類型 |
|-------------|--------|
| 字串 | 字串 |
| 前置詞 | 字串 |

## 簽章與傳回的型別

`startWithIgnoreCase(<string>,<string>)`

傳回布林值。

## 範例

`startWithIgnoreCase("rowing is great", "RO")`

傳回true。
