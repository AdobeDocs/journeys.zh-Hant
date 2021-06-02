---
product: adobe campaign
title: notEqualWithIgnoreCase
description: 了解函式notEqualWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 15%

---

# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

檢查包含第二個引數字串的第一個引數字串是否不同，忽略大小寫考量事項。

## 類別

String

## 函式語法

`notEqualWithIgnoreCase(<parameters>)`

## 參數

* 字串

## 簽名和返回類型

`notEqualWithIgnoreCase(<string>,<string>)`

傳回布林值。

## 範例

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
