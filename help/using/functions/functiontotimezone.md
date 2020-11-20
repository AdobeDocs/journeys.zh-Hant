---
product: adobe campaign
solution: Journey Orchestration
title: toTimeZone
description: 瞭解toTimeZone的函式
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 5%

---


# toTimeZone {#toTimeZone}

將字串值轉換為時區。

## 類別

轉換

## 函式語法

`toTimeZone(<parameter>)`

## 參數

| 參數 | 說明 |
|--- |--- |
| 字串 | 字串值必須包含區域ID。 它可以是欄位參考或運算式 |

## 簽名和傳回的類型

`toTimeZone(<string>)`

傳回時區。

## 範例

`toTimeZone("UTC")`

返回UTC。
