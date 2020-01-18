---
title: notEqualWithIgnoreCase
description: 瞭解函式notEqualWithIgnoreCase
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


# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

檢查具有第二個參數字串的第一個參數字串是否不同，忽略大小寫注意事項。

## 類別

字串

## 函式語法

`notEqualWithIgnoreCase(<parameters>)`

## 參數

* 字串

## 簽名和傳回的類型

`notEqualWithIgnoreCase(<string>,<string>)`

傳回布林值。

## 範例

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
