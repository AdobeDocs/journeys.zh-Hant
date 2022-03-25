---
product: adobe campaign
title: notEqualIgnoreCase
description: 瞭解函式notEqualIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 13%

---

# notEqualIgnoreCase {#notEqualIgnoreCase}

檢查帶有第二個參數字串的第一個參數字串是否不同，忽略大小寫注意事項。

## 類別

字串

## 函式語法

`notEqualIgnoreCase(<parameters>)`

## 參數

* 字串

## 簽名和返回的類型

`notEqualIgnoreCase(<string>,<string>)`

返回布爾值。

## 範例

`notEqualIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad")`
