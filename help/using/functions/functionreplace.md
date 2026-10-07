---
product: adobe campaign
title: replace
description: 瞭解函式取代
feature: Journeys
role: Developer
level: Experienced
exl-id: f30377c2-4d5e-4905-a972-8f4ccb272bc0
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
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
| Target | 字串(RegExp) |
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
