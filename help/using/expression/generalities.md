---
title: 一般性
description: 瞭解進階運算式通用性
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
source-git-commit: 239efa9592b011c70e2fc331df8f33820301253d

---


# 一般性 {#concept_rcy_qj5_dgb}

## 括弧和運算式優先順序{#section_edf_fks_bgb}

括弧可用來使複雜運算式更易讀。 _(&lt;expression>)_ 是等 _效的&lt;expression>_。 括弧也可用來定義評估順序和關聯性。

運算式會從左至右進行計算。 必須應用算術運算子的相關性：乘法和分部優先於加法和減法。 要強加特定順序，必須添加括弧來分隔操作。 例如：

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| 運算式 | 評估 |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39;優先於&#39;+&#39;:2 * 10被評估為→ 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>括弧會變更優先順序：(4 + 2)進行評估→ 6</li><li> 6 * 10 → 60</li></ul> |

## 區分大小寫{#section_lrb_xh5_dgb}

以下是不同的區分大小寫規則：

* 所有運算子（和或等）應該寫成小寫。 例如， _`<expression1>`且是`<expression2>`_有效的運算式，而運算式_`<expression1>` AND `<expression2>`_ 則否。
* 所有函式名稱都區分大小寫。 例如， _getBestSendTime()有效_ ，而函 __ 數GETBESTSENDTIME()無效。
* 欄位參考和常數值區分大小寫：它們不是語言的內建元素（與運算子和函式不同），而是由使用者編寫。

## 傳回的運算式類型{#section_gyc_435_53b}

運算式編輯器可以根據使用內容傳回不同的值。

| 進階運算式編輯器使用 | 預期的傳回運算式類型 |
|--- |--- |
| 條件（資料來源條件、日期條件） | 布林值 |
| 自訂計時器 | dateTimeOnly |
| 自訂時區 | 時區或字串（例如歐洲／巴黎） |
| 動作參數映射 | 任何 |
