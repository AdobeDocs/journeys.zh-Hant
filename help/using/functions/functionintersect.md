---
product: adobe campaign
title: 相交
description: 瞭解函式交集
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 12%

---

# 相交{#intersect}

返回兩個輸入清單中的公用值。 如果兩個清單之一為Null，則返回空清單。

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

`intersect(listString,listString)`:清單字串
`intersect(listDecimal,listDecimal)`:清單十進位
`intersect(listInteger,listInteger)`:listInteger
`intersect(listDateTime,listDateTime)`:清單日期時間
`intersect(listDateTimeOnly,listDateTimeOnly)`:listDateTimeOnly
`intersect(listDateOnly,listDateOnly)`:listDateOnly
`intersect(listDuration,listDuration)`:listDuration（持續時間）
`intersect(listBoolean,listBoolean)`:list布爾

返回清單。

## 範例

```json
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

返回 [&quot;體育&quot;、&quot;新聞&quot;]

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

返回配置檔案屬性和給定類別清單之間的公用項。

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
        @{myEvent.sport_interests}
)
```

返回配置檔案屬性和給定事件欄位之間的公用項。
