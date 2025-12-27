# 06_B_plan_selection.md

## 1. 文件目的

本文件說明在完成 A 方案（完整覆蓋測試）後，如何基於實際測試結果與觀察，
收斂出一組適合在時間、成本或資源受限情境下執行的測試集合（B 方案）。

B 方案並非取代 A 方案，  
而是建立在 A 方案結果之上的**策略性取捨**。

---

## 2. B 方案的設計前提

B 方案的選擇依據以下前提條件：

- A 方案（78 項測試）已完整執行
- 測試結果已整理並分析於 `03_result_analysis_and_grouping.md`
- 測試行為與風險特性已在 `04_summary_report.md` 中彙整

因此，B 方案不是理論假設，  
而是根據實際測試經驗所形成的精簡測試集。

---

## 3. 測試項目收斂原則

B 方案測試項目依下列原則進行選擇：

### 3.1 優先保留高風險項目

以下類型的測試優先保留：

- 涉及核心 API 資源的基本功能
- 曾出現行為不一致或錯誤回應模糊的測試
- 能快速暴露結構或行為異常的測試

---

### 3.2 保留代表性錯誤情境

錯誤處理測試中：

- 不追求完整錯誤排列組合
- 保留能代表整體錯誤表面的測試
- 聚焦於錯誤狀態碼與回應一致性

---

### 3.3 移除低訊號或高度重複項目

以下類型的測試通常被移除或合併：

- 行為與結果高度重複的測試
- 僅參數值不同但不影響行為判斷的測試
- 在 A 方案中已證實穩定且無異常的變形測試

---

## 4. B 方案測試項目類型

B 方案測試項目主要包含：

- 每個核心 API 資源至少一項 Contract 測試
- 每個核心 API 資源至少一項 Behavior 測試
- 少量但具代表性的 Error Handling 測試

此組合可在最小成本下，  
快速驗證 API 的結構穩定性與基本行為合理性。

---

## 5. B 方案的適用情境

B 方案適合用於下列情境：

- 回歸測試（Regression Testing）
- API 文件更新後的快速驗證
- 時間或請求配額受限的測試執行
- 僅需確認 API 是否維持基本可用性時

---

## 6. B 方案與 A 方案的關係

| 面向     | A 方案                 | B 方案               |
|----------|-----------------------|----------------------|
| 目的     | 完整學習與全面驗證      | 快速驗證與回歸        |
| 覆蓋範圍 | 全部功能與變形          | 核心功能與高風險項目   |
| 測試數量 | 高                     | 低                   |
| 執行成本 | 高                     | 低                   |
| 適用時機 | 初次驗證 / 深度分析     | 日常驗證 / 限制情境    |


---

## 7. 結論

B 方案並非降低測試品質，  
而是在已完成完整測試的前提下，進行有依據的收斂。

透過 A → B 的設計，本專案展示了：

- 完整測試後進行分析與歸納的能力
- 在實務限制下進行合理取捨的能力
- 對測試成本與風險的工程化理解

---

---

## 1. Document Purpose

This document describes how a reduced test set (Plan B) is derived after completing the full coverage test plan (Plan A).

Plan B is designed for scenarios where time, cost, or resources are limited,  
and is based entirely on actual test results and observations rather than assumptions.

---

## 2. Preconditions for Plan B

Plan B is derived under the following conditions:

- Plan A (78 test cases) has been fully executed
- Test results have been analyzed in `03_result_analysis_and_grouping.md`
- Key findings and risk patterns are summarized in `04_summary_report.md`

Plan B is therefore a result-driven test selection, not a theoretical shortcut.

---

## 3. Test Selection Principles

Plan B test cases are selected based on the following principles:

### 3.1 Prioritize High-Risk Test Cases

Priority is given to test cases that:

- Involve core API resources
- Exposed inconsistent behavior or ambiguous error handling
- Can quickly reveal structural or behavioral regressions

---

### 3.2 Retain Representative Error Scenarios

For error handling tests:

- Exhaustive permutations are avoided
- Representative error surfaces are retained
- Focus is placed on status code and response consistency

---

### 3.3 Remove Low-Signal or Redundant Tests

The following types of tests are typically removed or merged:

- Tests with highly repetitive behavior and outcomes
- Parameter variations that do not affect behavior interpretation
- Variants proven stable during Plan A execution

---

## 4. Composition of Plan B

Plan B typically includes:

- At least one Contract test per core API resource
- At least one Behavior test per core API resource
- A small number of representative Error Handling tests

This composition enables efficient validation with minimal execution cost.

---

## 5. Applicable Scenarios for Plan B

Plan B is suitable for:

- Regression testing
- Quick verification after API documentation changes
- Environments with limited execution time or request quotas
- Situations requiring basic API availability checks

---

## 6. Relationship Between Plan A and Plan B

| Aspect          | Plan A                             | Plan B                                 |
|-----------------|------------------------------------|----------------------------------------|
| Purpose         | Full learning and validation       | Quick validation and regression        |
| Coverage        | All features and variants          | Core features and high-risk cases      |
| Test Volume     | High                               | Low                                    |
| Execution Cost  | High                               | Low                                    |
| Usage Timing    | Initial validation / deep analysis | Routine checks / constrained scenarios |


---

## 7. Conclusion

Plan B does not reduce testing quality;  
it represents a deliberate and informed reduction based on full test coverage.

Through the A → B approach, this project demonstrates:

- The ability to analyze results after comprehensive testing
- The ability to make informed trade-offs under constraints
- An engineering-oriented understanding of test cost and risk
