---
title: getBestSendTime
description: 瞭解getBestSendTime函式
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# getBestSendTime {#getBestSendTime}

提供將電子郵件傳送至個人的最佳時機預測時間。

此函式使用在平台中計算的分數。 分數會根據過去的行為，計算日後點按或開啟電子郵件的傾向。 請注意，計算分數的演算法需要一定數量的資料才能運作。 因此，當資料不足時，將會套用預設時間。 For more information, see [](../building-journeys/wait-activity.md).

若要使用此函式，則需 [要命](../event/selecting-the-namespace.md) 名空間。

>[!NOTE]
>
>請注意，如果沒有足夠的資料來執行計算，則可能無法使用最佳傳送時間分數。 在此情況下，您會在發佈時收到預設時間的通知。

## 類別

Adobe Experience Platform

## 函式語法

`getBestSendTime(<parameters>)`

## 參數

| 參數 | 說明 | 類型 |
|--- |--- |--- |
| 時間量 | 從目前時間開始考慮的小時數(最大：168)以最佳化電子郵件傳送 | `<integer>` |
| 優化類型 | 「開啟」或「按一下」 | `<string>` |
| 預設等待時間（以小時為單位） | 萬一預測性傳送時間分數不可用 | `<integer>` |

## 簽名和傳回的類型

`getBestSendTime(<integer>,<string>,<integer>)`

傳回dateTime。

## 範例

getBestSendTime(12,&quot;open&quot;,8)

說明：

函式會在接下來的12小時內傳送訊息，以最佳化歷程例項中個人開啟訊息的可能性。 如果沒有足夠的資料來執行計算，則返回的時間為當前時間的8小時。
