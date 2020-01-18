---
title: toTimeZone
description: 瞭解toTimeZone的函式
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
