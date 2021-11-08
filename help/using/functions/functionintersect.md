---
product: adobe campaign
title: 相交
description: 了解函式相交
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 12%

---

# 相交{#intersect}

傳回兩個輸入清單中的公用值。 如果兩個清單之一為null，則返回空清單。

## 類別

清單

## 函式語法

`intersect(<parameters>)`

## 參數

| 參數 | 類型 |
|-----------|------------------|
| 清單1 | 清單 |
| 清單2 | 清單 |

## 簽名和返回的類型

`intersect(listString,listString)`:listString
`intersect(listDecimal,listDecimal)`:listDecimal
`intersect(listInteger,listInteger)`:listInteger
`intersect(listDateTime,listDateTime)`:listDateTime
`intersect(listDateTimeOnly,listDateTimeOnly)`:listDateTimeOnly
`intersect(listDateOnly,listDateOnly)`:listDateOnly
`intersect(listDuration,listDuration)`:listDuration
`intersect(listBoolean,listBoolean)`:listBoolean

傳回清單。

## 範例

```json
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

傳回 [&quot;sports&quot;、&quot;news&quot;]

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

傳回設定檔屬性和指定類別清單之間的通用項目。

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
        @{myEvent.sport_interests}
)
```

傳回設定檔屬性和指定事件欄位之間的通用項目。
