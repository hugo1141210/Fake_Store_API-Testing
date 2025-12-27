# 01_test_plan.md

## 1. 專案目的與背景

本專案為一個 API 測試練習專案，測試對象為公開的 REST API —— Fake Store API。  
專案目標在於實際操作 API 測試流程，驗證 API 在正常與異常情境下的行為一致性、回應結構穩定性，以及基本錯誤處理能力。

此專案定位為技術練習與能力展示，而非產品等級的完整品質保證（QA）活動。

---

## 2. 測試範圍（Scope）

### 2.1 測試對象

- Fake Store API（公開 REST API）
- 涵蓋的 API 資源：
  - Products
  - Users
  - Carts
  - Authentication / Login

### 2.2 測試內容包含

- API 功能行為驗證
- 回應資料結構與欄位驗證
- 參數變形（Query / Path Parameter）測試
- 基本錯誤處理行為驗證

### 2.3 不包含的項目（Out of Scope）

- 前端 UI 測試
- 效能、壓力或負載測試（Load / Stress Testing）
- 資安或滲透測試（Security / Penetration Testing）
- 第三方系統整合測試

---

## 3. 測試類型（Test Types）

本專案使用下列三種測試類型：

### 3.1 Contract Testing（契約測試）

- 驗證 API 回應是否符合預期的資料結構
- 包含欄位存在性、資料型別與基本結構穩定性
- 不關注商業邏輯正確性

### 3.2 Behavior Testing（行為測試）

- 驗證 API 功能行為是否符合預期
- 包含成功情境（Happy Path）與基本功能邏輯檢查

### 3.3 Error Handling Testing（錯誤處理測試）

- 驗證 API 在異常輸入或不存在資源情境下的回應
- 包含錯誤狀態碼與回應行為一致性
- 不追求完整錯誤排列組合，僅驗證具代表性的錯誤面

---

## 4. 測試策略概述

### 4.1 A 方案（完整覆蓋方案）

A 方案用於學習與完整驗證目的，測試設計重點為：

- 覆蓋所有主要 API 功能與資源
- 覆蓋所有文件中出現的參數變形
- 每一功能皆涵蓋 Contract、Behavior 與 Error Handling 三種測試類型

A 方案共包含 78 個測試項目，作為本專案的完整測試基準。

### 4.2 B 方案（收斂方案）

B 方案為資源或時間受限情境下的回歸測試策略，設計原則為：

- 基於 A 方案實際測試結果進行收斂
- 保留高風險、高訊號的測試項目
- 作為快速驗證 API 基本穩定性的最小測試集合

B 方案測試項目將另行定義於 `06_B_plan_selection.md`。

---

## 5. 測試工具與執行方式（概述）

- 使用 Postman 建立 API 測試集合（Collection）
- 使用 Newman CLI 執行測試並產出結構化測試結果
- 測試結果以 JSON 格式保存，作為可重跑與可驗證的測試證據

詳細執行流程請參考 `05_execution_plan.md`。

---

## 6. 文件關係說明

本測試計畫文件為整體測試設計之基礎，後續文件角色如下：

- `02_test_cases_A78.md`：A 方案完整測試項目清單
- `03_result_analysis_and_grouping.md`：測試結果分析與分組
- `04_summary_report.md`：測試總結報告（對外說明）
- `05_execution_plan.md`：測試執行流程與工具使用
- `06_B_plan_selection.md`：B 方案測試項目收斂清單

---

---

## 1. Purpose and Background

This project is an API testing practice project targeting a public REST API, Fake Store API.  
The objective is to practice real-world API testing workflows by validating API behavior consistency, response structure stability, and basic error handling under both normal and exceptional scenarios.

This project is intended for technical practice and capability demonstration, rather than a full production-level QA engagement.

---

## 2. Scope

### 2.1 Test Target

- Fake Store API (Public REST API)
- Covered API resources:
  - Products
  - Users
  - Carts
  - Authentication / Login

### 2.2 In Scope

- API functional behavior validation
- Response structure and field verification
- Parameter variations (Query / Path parameters)
- Basic error handling behavior validation

### 2.3 Out of Scope

- Frontend UI testing
- Performance, load, or stress testing
- Security or penetration testing
- Third-party integration testing

---

## 3. Test Types

The following test types are used in this project:

### 3.1 Contract Testing

- Validates whether API responses conform to the expected data structure
- Includes field existence, data types, and basic schema stability
- Does not verify business logic correctness

### 3.2 Behavior Testing

- Validates functional behavior of API endpoints
- Includes happy path scenarios and basic logic verification

### 3.3 Error Handling Testing

- Validates API responses under invalid input or non-existent resource scenarios
- Includes status codes and response behavior consistency
- Representative error surfaces are tested instead of exhaustive permutations

---

## 4. Test Strategy Overview

### 4.1 Plan A (Full Coverage Plan)

Plan A is designed for learning and full verification purposes:

- Covers all major API endpoints and resources
- Covers all documented parameter variations
- Each function includes Contract, Behavior, and Error Handling tests

Plan A consists of 78 test cases and serves as the complete testing baseline.

### 4.2 Plan B (Reduced Plan)

Plan B is intended for constrained time or resource scenarios:

- Derived from actual results of Plan A
- Retains high-risk and high-signal test cases
- Serves as a minimal regression test set for basic API stability verification

Plan B test cases are defined in `06_B_plan_selection.md`.

---

## 5. Tools and Execution Overview

- Postman is used to create API test collections
- Newman CLI is used to execute tests and generate structured results
- Test results are stored in JSON format as reproducible test evidence

For detailed execution steps, refer to `05_execution_plan.md`.

---

## 6. Document Relationship

This document defines the overall testing plan. Related documents include:

- `02_test_cases_A78.md`: Complete test case list for Plan A
- `03_result_analysis_and_grouping.md`: Test result analysis and grouping
- `04_summary_report.md`: Test summary report
- `05_execution_plan.md`: Execution plan and tooling details
- `06_B_plan_selection.md`: Reduced Plan B test selection
