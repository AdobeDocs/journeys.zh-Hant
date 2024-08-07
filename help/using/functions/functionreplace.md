---
product: adobe campaign
title: replace
description: 瞭解函式取代
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: f30377c2-4d5e-4905-a972-8f4ccb272bc0
source-git-commit: 8980df5cc238a7195f01a1631e418a8de677fbea
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 12%

---

# replace {#replace}

以基礎字串中的取代字串取代符合目標字串的第一個專案。

例如，取代會從字串的開頭到結尾進行，將字串「aaa」中的「aa」取代為「b」將會產生「ba」而非「ab」。

## 類別

字串

## 函式語法

`replace(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|--------------|
| 基底 | 字串 |
| 目標 | 字串(RegExp) |
| 取代 | 字串 |

## 簽章與傳回的型別

`replace(<base>,<target>,<replacement>)`

傳回字串。

## 範例 1

`replace("Hello World", "l", "x")`

傳回「Hexlo World」。

## 範例 2 {#example_2}

由於目標引數是RegExp，因此根據您要取代的字串，您可能需要將部分字元逸出。 其範例如下：

* 要評估的字串： `|OFFER_A|OFFER_B`
* 由設定檔屬性`#{ExperiencePlatform.myFieldGroup.profile.myOffers}`提供
* 要取代的字串： `|OFFER_A`
* 字串取代為： `''`
* 您必須在`|`字元前新增`\\`。

運算式為：

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|OFFER_A', '')`

傳回的字串是： `|OFFER_B`

您也可以建置要由指定屬性取代的字串：

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|' + #{ExperiencePlatform.myFieldGroup.profile.myOfferCode}, '')`
