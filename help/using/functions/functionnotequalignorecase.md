---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: 瞭解函式notEqualWithIgnoreCase
feature: 旅程
role: 資料工程師
level: 經驗豐富
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 12%

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
