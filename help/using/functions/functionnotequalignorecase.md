---
product: adobe campaign
title: notEqualIgnoreCase
description: 瞭解函式notEqualIgnoreCase
feature: Journeys
role: Developer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 13%

---

# notEqualIgnoreCase {#notEqualIgnoreCase}

檢查第一個引數字串是否與第二個引數字串不同，忽略大小寫考量。

## 類別

字串

## 函式語法

`notEqualIgnoreCase(<parameters>)`

## 參數

* 字串

## 簽章與傳回的型別

`notEqualIgnoreCase(<string>,<string>)`

傳回布林值。

## 範例

`notEqualIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad")`
