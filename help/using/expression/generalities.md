---
product: adobe campaign
solution: Journey Orchestration
title: 一般性
description: 瞭解進階運算式通用性
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---


# 一般性 {#concept_rcy_qj5_dgb}

## 括弧和運算式優先順序{#section_edf_fks_bgb}

括弧可用來使複雜運算式更易讀。 _(&lt;expression>)_ 等於 _&lt;expression>_。括弧也可用來定義評估順序和關聯性。

運算式會從左至右進行計算。 必須應用算術運算子的相關性：乘法和分部優先於加法和減法。 為了強加特定順序，必須添加括弧來分隔操作。 例如：

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| 運算式 | 評估 |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39;優先於&#39;+&#39;:2 * 10被評估為→ 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>括弧會變更優先順序：(4 + 2)進行評估→ 6</li><li> 6 * 10 → 60</li></ul> |

## 區分大小寫{#section_lrb_xh5_dgb}

以下是不同的區分大小寫規則：

* 所有運算子（和或等） 應該寫成小寫。 例如，_`<expression1>`和`<expression2>`_&#x200B;是有效的運算式，而運算式&#x200B;_`<expression1>`AND`<expression2>`_&#x200B;則否。
* 所有函式名稱都區分大小寫。 例如，_inSegment()_&#x200B;是有效的，而函式&#x200B;_INSEGMENT()_&#x200B;則否。
* 欄位參考和常數值區分大小寫：它們不是語言的內建元素（與運算子和函式不同），而是由使用者編寫。

## 傳回的運算式類型{#section_gyc_435_53b}

運算式編輯器可以根據使用內容傳回不同的值。

| 進階運算式編輯器使用 | 預期的傳回運算式類型 |
|--- |--- |
| 條件（資料來源條件、日期條件） | 布林值 |
| 自訂計時器 | dateTimeOnly |
| 動作參數映射 | 任何 |
