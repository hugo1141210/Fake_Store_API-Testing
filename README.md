# Fake_Store_API-Testing

## 專案簡介

本專案為一個 **第三方公開 API（Fake Store API）之 API 測試專案**，  
目標在於展示我對 **API 測試流程、測試設計、實際執行，以及結果分析與取捨能力** 的理解與實作。

本專案並非單純列出測試案例，而是完整呈現：

- 從「全覆蓋測試」開始
- 到「基於結果進行分析與收斂」
- 最終形成可在現實限制下使用的測試方案

---

## 專案目標

- 驗證 Fake Store API 主要功能與行為
- 建立一套可重跑、可驗證的 API 測試流程
- 展示如何在完整測試後，進行合理的測試取捨（Plan A → Plan B）
- 證明具備 API 測試的實務執行能力，而非只會「照表跑測試」

---

## 測試對象

- API 名稱：Fake Store API ( https://fakestoreapi.com/ )
- API 類型：公開第三方 REST API
- 測試範圍：
  - Products
  - Users
  - Carts
  - Authentication

---

## 測試工具與技術

- Postman  
  - 建立 API Collection 與 Environment
  - 定義測試請求與基本斷言

- Newman  
  - 透過 CLI 執行測試集合
  - 產出結構化與可視化測試結果

- Newman Reporter (HTML Extra)  
  - 產出人類可閱讀的 HTML 測試報告

---

## 測試策略概述

### Plan A：完整測試方案

- 共 78 項測試案例
- 覆蓋所有主要 API 功能與參數變形
- 包含：
  - Contract Testing
  - Behavior Testing
  - Error Handling Testing
- 目的：完整理解 API 行為與風險輪廓

詳細內容請參考 `01_test_plan.md` 與 `02_test_cases_A78.md`。

### Plan B：收斂測試方案

- 基於 Plan A 實際執行結果進行取捨
- 保留高風險與高訊號測試
- 適用於：
  - 回歸測試
  - 時間 / 配額 / 成本受限情境

詳細分析請參考 `06_B_plan_selection.md`。

---

## 測試結果呈現

- HTML 報告  
  - 用於人類閱讀與成果展示

- JSON 結果  
  - 用於 QA 分析與測試行為驗證

測試結果的分析與分組說明請參考：

- `03_result_analysis_and_grouping.md`
- `04_summary_report.md`

---

## 專案重點說明

- 本專案以「實際跑過完整測試」為前提，而非僅列出測試案例
- 強調測試設計、執行與結果分析的完整流程
- 展示在完整測試後，能基於風險與成本進行理性取捨


## 專案檔案目錄

.
├── docs
│   ├── 01_test_plan.md                         # Test strategy, scope definition, and test taxonomy
│   ├── 02_test_cases_A78.md                    # Full test case list (Plan A, 78 cases)
│   ├── 03_result_analysis_and_grouping.md      # Result analysis, grouping, and behavior observations                         
│   ├── 04_summary_report.md                    # High-level summary of findings and conclusions
│   ├── 05_execution_plan.md                    # How tests were executed and results generated
│   └── 06_B_plan_selection.md                  # Reduced test plan derived from Plan A results
│
├── postman
│   ├── FakeStoreAPI.postman_collection.json    # Postman collection mapping to Plan A test cases                            
│   └── FakeStoreAPI.postman_environment.json   # Environment variables (base URL, reusable parameters)                               
│
├── reports
│   ├── newman-report.html                      # Human-readable HTML test report
│   └── newman-report.json                      # Structured test results for QA analysis
│
└── README.md                                   # Project overview and navigation



---
---

## Project Overview

This project is an **API testing project for a third-party public API (Fake Store API)**.  
It is intended to demonstrate my hands-on understanding and implementation of **API testing workflows**, including **test design, execution, result analysis, and informed trade-offs**.

Rather than simply listing test cases, this project presents a complete process:

- starting from **full coverage testing**
- moving to **analysis and consolidation based on results**
- and ultimately forming a test plan that can be used under real-world constraints

---

## Project Objectives

- Validate the key functionalities and behaviors of the Fake Store API
- Build a repeatable and verifiable API testing workflow
- Demonstrate how to make informed test scope trade-offs after full testing (Plan A → Plan B)
- Prove practical API testing capability beyond checklist-style execution

---

## Test Target

- API Name: Fake Store API ( https://fakestoreapi.com/ )
- API Type: Public third-party REST API
- Test Scope:
  - Products
  - Users
  - Carts
  - Authentication

---

## Tools and Technologies

- Postman  
  - Create API collections and environments  
  - Define test requests and basic assertions

- Newman  
  - Execute collections via CLI  
  - Generate structured and visualized test results

- Newman Reporter (HTML Extra)  
  - Generate human-readable HTML test reports

---

## Test Strategy Summary

### Plan A: Full Coverage Plan

- 78 test cases in total
- Covers all major API features and parameter variants
- Includes:
  - Contract Testing
  - Behavior Testing
  - Error Handling Testing
- Purpose: gain a complete understanding of API behavior and its risk surface

For details, see `01_test_plan.md` and `02_test_cases_A78.md`.

### Plan B: Reduced Plan

- Derived from actual execution results of Plan A
- Retains high-risk and high-signal tests
- Suitable for:
  - Regression testing
  - Time/quota/cost-constrained scenarios

For analysis, see `06_B_plan_selection.md`.

---

## Test Results

- HTML Report  
  - For human-readable review and presentation

- JSON Output  
  - For QA analysis and verification of test behavior

For result analysis and grouping, see:

- `03_result_analysis_and_grouping.md`
- `04_summary_report.md`

---

## Key Highlights

- This project is based on actually executing the full test plan, not merely listing test cases
- Emphasizes the complete workflow: test design, execution, and result analysis
- Demonstrates rational test scope decisions based on risk and cost after full coverage testing

---

## Directory structure

.
├── docs
│   ├── 01_test_plan.md                         # Test strategy, scope definition, and test taxonomy
│   ├── 02_test_cases_A78.md                    # Full test case list (Plan A, 78 cases)
│   ├── 03_result_analysis_and_grouping.md      # Result analysis, grouping, and behavior observations                         
│   ├── 04_summary_report.md                    # High-level summary of findings and conclusions
│   ├── 05_execution_plan.md                    # How tests were executed and results generated
│   └── 06_B_plan_selection.md                  # Reduced test plan derived from Plan A results
│
├── postman
│   ├── FakeStoreAPI.postman_collection.json    # Postman collection mapping to Plan A test cases                            
│   └── FakeStoreAPI.postman_environment.json   # Environment variables (base URL, reusable parameters)                               
│
├── reports
│   ├── newman-report.html                      # Human-readable HTML test report
│   └── newman-report.json                      # Structured test results for QA analysis
│
└── README.md                                   # Project overview and navigation
