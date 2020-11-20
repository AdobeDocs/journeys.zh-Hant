---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: 瞭解函式notEqualWithIgnoreCase
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 10%

---


# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

檢查具有第二個參數字串的第一個參數字串是否不同，忽略大小寫注意事項。

## 類別

String

## 函式語法

`notEqualWithIgnoreCase(<parameters>)`

## 參數

* 字串

## 簽名和傳回的類型

`notEqualWithIgnoreCase(<string>,<string>)`

傳回布林值。

## 範例

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
