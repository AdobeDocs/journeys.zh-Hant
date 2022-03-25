---
product: adobe campaign
title: 一般性
description: 瞭解高級表達式的一般性
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

## 括弧和表達式優先順序{#section_edf_fks_bgb}

括弧可用於使複雜表達式更易讀。 _(&lt;expression>)_ 等於 _&lt;expression>_。 括弧也可用於定義評估順序和相關性。

表達式將從左到右進行計算。 必須應用算術運算子的相關性：乘法和除法優先於加法和減法。 要強加特定順序，必須添加括弧來限定操作。 例如：

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| 運算式 | 評估 |
|--- |--- |
| `4 + 2 * 10` | <ul><li>「*」優先於「+」：2 * 10被評估→ 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>括弧會更改優先順序：(4 + 2)被評估→ 6</li><li> 6 * 10 → 60</li></ul> |

## 區分大小寫{#section_lrb_xh5_dgb}

以下是不同的區分大小寫規則：

* 所有運算子（和或等） 應該寫成小寫。 比如說， _`<expression1>`和`<expression2>`_ 是有效的表達式，而表達式 _`<expression1>`和`<expression2>`_ 不。
* 所有函式名稱區分大小寫。 比如說， _inSegment()_ 有效，而函式 _INSEGMENT()_ 不。
* 欄位引用和常數值區分大小寫：它們不是語言的內置元素（與運算子和函式不同），它們由最終用戶編寫。

## 返回的表達式類型{#section_gyc_435_53b}

根據使用的上下文，表達式編輯器可以返回不同的值。

| 高級表達式編輯器用法 | 應為返回的表達式類型 |
|--- |--- |
| 條件（資料源條件、日期條件） | 布林值 |
| 自定義計時器 | 日期僅時間 |
| 操作參數映射 | 任何 |
