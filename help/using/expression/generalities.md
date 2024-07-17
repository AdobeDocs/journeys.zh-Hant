---
product: adobe campaign
title: 一般性
description: 瞭解進階運算式一般性
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ba474219-7c9e-4f93-8e9c-16c317131614
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 3%

---

# 一般性 {#concept_rcy_qj5_dgb}

## 括弧和運算式優先順序{#section_edf_fks_bgb}

括弧可用來讓複雜的運算式更容易閱讀。 _（&lt;運算式>）_&#x200B;相當於&#x200B;_&lt;運算式>_。 括弧也可用來定義評估順序和關聯性。

運算式將由左至右評估。 必須套用算術運運算元的關聯性：乘法和除法優先於加法和減法。 為了強制特定順序，必須加入括弧以分隔操作。 例如：

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| 運算式 | 評估 |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39;優先順序高於&#39;+&#39;：2 * 10→20計算</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>括弧會變更優先順序： (4 + 2)的評估方式→6</li><li> 6 * 10 → 60</li></ul> |

## 區分大小寫{#section_lrb_xh5_dgb}

以下是不同的區分大小寫規則：

* 所有運運算元（和、或等） 應該寫成小寫。 例如，_`<expression1>`和`<expression2>`_&#x200B;是有效的運算式，而運算式&#x200B;_`<expression1>`AND`<expression2>`_&#x200B;則否。
* 所有函式名稱都區分大小寫。 例如，_inSegment()_&#x200B;有效，而函式&#x200B;_INSEGMENT()_&#x200B;無效。
* 欄位參照和常數值區分大小寫：它們不是語言的內建元素（與運運算元和函式相反），而是由一般使用者撰寫。

## 傳回的運算式型別{#section_gyc_435_53b}

根據使用內容，運算式編輯器可傳回不同的值。

| 進階運算式編輯器使用 | 預期傳回的運算式型別 |
|--- |--- |
| 條件（資料來源條件、日期條件） | 布林值 |
| 自訂計時器 | dateTimeOnly |
| 動作引數對應 | 任何 |
