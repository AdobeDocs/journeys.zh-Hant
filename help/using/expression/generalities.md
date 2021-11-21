---
product: adobe campaign
title: 一般性
description: 了解進階運算式一般性
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ba474219-7c9e-4f93-8e9c-16c317131614
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 5%

---

# 一般性 {#concept_rcy_qj5_dgb}

## 括弧和運算式優先順序{#section_edf_fks_bgb}

括弧可用來讓複雜運算式更容易閱讀。 _(&lt;expression>)_ 等同於 _&lt;expression>_. 括弧也可用於定義評估順序和關聯性。

將從左到右評估表達式。 必須應用算術運算子的相關性：乘法和分部優先於加法和減法。 為了強加特定順序，必須加上括弧來分隔操作。 例如：

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| 運算式 | 評估 |
|--- |--- |
| `4 + 2 * 10` | <ul><li>「*」優先於「+」：2 * 10被評估→ 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>括弧會變更優先順序：(4 + 2)被評估→ 6</li><li> 6 * 10 → 60</li></ul> |

## 區分大小寫{#section_lrb_xh5_dgb}

以下是不同的區分大小寫規則：

* 所有運算子（和等） 應寫成小寫。 例如， _`<expression1>`和`<expression2>`_ 是有效的運算式，而運算式 _`<expression1>`和`<expression2>`_ 不是。
* 所有函式名稱均區分大小寫。 例如， _inSegment()_ 有效，而函式 _INSEGMENT()_ 不是。
* 欄位參考和常數值區分大小寫：它們不是語言的內建元素（與運算子和函式相反），而是由最終用戶編寫的。

## 返回的表達式類型{#section_gyc_435_53b}

視使用內容而定，運算式編輯器可傳回不同的值。

| 進階運算式編輯器用法 | 預期的返回表達式類型 |
|--- |--- |
| 條件（資料來源條件、日期條件） | 布林值 |
| 自訂計時器 | dateTimeOnly |
| 動作參數對應 | 任何 |
