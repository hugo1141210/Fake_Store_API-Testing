# 05_execution_plan.md

## 1. 文件目的

本文件說明 Fake Store API 測試專案的實際執行方式，  
重點在於說明測試是如何被實際執行，以及測試結果如何被產出與保存。

本文件描述的是實務執行層面的做法，  
測試設計與策略已定義於 `01_test_plan.md`。

---

## 2. 專案與執行環境

### 2.1 作業環境

- 作業系統：Windows
- Shell：PowerShell
- 專案以本機目錄執行（非 CI 環境）

---

### 2.2 測試工具

- **Postman**
  - 用於建立 API 測試 Collection 與 Environment
  - 定義 Request、參數與基本測試斷言

- **Newman（Postman CLI）**
  - 用於以指令列方式執行 Postman Collection
  - 作為測試自動化與結果輸出的主要工具

- **newman-reporter-htmlextra**
  - 用於產出 HTML 格式測試報告
  - 提供可視化的測試結果呈現

---

## 3. 測試相關檔案

### 3.1 Collection

- 檔案內容：
  - 包含 A 方案共 78 項測試案例
  - 涵蓋 Products、Users、Carts、Authentication 等 API 資源
- Collection 作為測試案例的單一事實來源（source of truth）

---

### 3.2 Environment

- Environment 定義：
  - API Base URL
  - 可重用參數（例如資源 ID、錯誤測試用值）

此設計避免將測試資料硬編碼於 Request 中，  
提升測試的可維護性與可重跑性。

---

## 4. 測試執行方式說明

### 4.1 執行流程概述

測試執行流程採取以下方式：

1. 透過 Postman 檢查 Collection 與 Environment 設定是否正確
2. 使用 Newman 執行完整測試集合
3. 於執行過程中即時觀察測試結果
4. 執行完成後產出測試報告檔案
5. 將測試結果整理至分析文件（03）

---

### 4.2 Reporter 使用說明

- **CLI 輸出**
  - 即時顯示測試執行狀態
  - 用於確認測試是否正常完成

- **HTML 報告**
  - 提供整體測試結果的可視化呈現
  - 適合人工檢視與成果展示

---

## 5. 測試結果輸出與用途

### 5.1 輸出成果

測試執行完成後，會產出下列結果檔案：

- **HTML 測試報告**
  - 作為主要對人閱讀的成果文件
  - 用於展示測試覆蓋與整體結果

- **JSON 測試結果**
  - 保留完整結構化測試資訊
  - 用於 QA 除錯與測試腳本驗證

---

### 5.2 為何同時保留不同格式的報告

- HTML 報告：
  - 易於閱讀與說明
  - 適合對外展示測試成果

- JSON 結果：
  - 提供完整且精確的測試執行細節
  - 適合分析測試失敗原因或驗證測試正確性

本專案將 JSON 視為技術驗證證據，  
HTML 視為成果呈現文件。

---

## 6. 執行策略與注意事項

- 測試以序列方式執行，不進行平行或高頻請求
- 不進行效能、壓力或安全性測試
- 測試失敗不直接視為系統缺陷，需結合情境判斷其原因

實際觀察與判斷結果將反映於 `03_result_analysis_and_grouping.md`。

---

## 7. 與後續文件的關係

本文件所描述的執行方式，作為下列文件的實務基礎：

- `03_result_analysis_and_grouping.md`
- `04_summary_report.md`
- `06_B_plan_selection.md`

---

---

## 1. Document Purpose

This document describes how the Fake Store API testing project was executed in practice.  
The focus is on explaining how the tests were run and how test results were generated and preserved.

This document covers execution-level practices.  
Test design and strategy are defined in `01_test_plan.md`.

---

## 2. Project and Execution Environment

### 2.1 Execution Environment

- Operating System: Windows
- Shell: PowerShell
- Tests were executed locally (non-CI environment)

---

### 2.2 Testing Tools

- **Postman**
  - Used to define API test collections and environments
  - Defines requests, parameters, and basic test assertions

- **Newman (Postman CLI)**
  - Used to execute Postman collections via command-line interface
  - Serves as the primary tool for automated execution and result generation

- **newman-reporter-htmlextra**
  - Used to generate HTML-based test reports
  - Provides a more readable, visual representation of test results

---

## 3. Test Artifacts

### 3.1 Collection

- Contents:
  - Includes 78 test cases defined under Plan A
  - Covers Products, Users, Carts, and Authentication resources
- The collection serves as the single source of truth for test cases

---

### 3.2 Environment

- The environment defines:
  - API base URL
  - Reusable parameters (e.g., resource IDs, invalid test values)

This approach avoids hardcoding test data directly in requests and improves maintainability and repeatability.

---

## 4. Test Execution Overview

### 4.1 Execution Flow

The test execution process follows these steps:

1. Verify the correctness of the collection and environment configuration
2. Execute the complete test collection using Newman
3. Observe execution status during runtime
4. Generate test result artifacts upon completion
5. Summarize findings in the analysis document (03)

---

### 4.2 Reporter Usage

- **CLI Output**
  - Provides real-time visibility into test execution status
  - Used to confirm successful execution

- **HTML Report**
  - Provides a visual summary of overall test results
  - Used for human-readable review and presentation

---

## 5. Test Results and Usage

### 5.1 Output Artifacts

After execution, the following artifacts are produced:

- **HTML Test Report**
  - Primary human-readable report
  - Used to present test coverage and overall outcomes

- **JSON Test Results**
  - Structured test execution data
  - Used for QA analysis and debugging test script issues

---

### 5.2 Rationale for Multiple Report Formats

- HTML reports:
  - Easy to read and present
  - Suitable for communicating test outcomes

- JSON results:
  - Preserve complete structured execution data
  - Suitable for validating test behavior and investigating failures

In this project, JSON output is treated as technical verification evidence,  
while HTML output is treated as a presentation artifact.

---

## 6. Execution Strategy and Considerations

- Tests are executed sequentially to avoid excessive request frequency
- No performance, load, or security testing is performed
- Test failures are not immediately treated as defects and are evaluated based on context

Observations and conclusions are documented in `03_result_analysis_and_grouping.md`.

---

## 7. Relationship to Other Documents

This execution approach supports the following documents:

- `03_result_analysis_and_grouping.md`
- `04_summary_report.md`
- `06_B_plan_selection.md`
