# 02_test_cases_A78.md

### 文件定位說明

本文件為 **Plan A（A 方案）之完整測試案例清單**，  
目的在於對 Fake Store API 提供的所有主要功能與變形進行**全面測試與完整紀錄**。

本清單中的每一列皆為：

- 一個**可獨立執行的 Test Case**
- 可直接對應至一個 Postman request
- 或對應 Newman data-driven execution 中的一筆測試資料

本文件不負責說明測試策略或取捨邏輯，  
僅負責**完整列舉「所有被測過的項目」**，作為後續分析與收斂的基礎。

---

### 使用說明

- Test Case 依 API Domain（Products / Carts / Users / Auth）分段編排
- 每個 Test Item（ITEM-XXX）固定包含：
  - Contract
  - Behavior
  - Error Handling  
  三種類型測試
- 本文件對應之測試結果與觀察，已整理於：
  - `03_result_analysis_and_grouping.md`
  - `04_summary_report.md`

---

### Document Purpose

This document represents the **complete test case list for Plan A**,  
designed to fully validate all major functionalities and variants provided by the Fake Store API.

Each row in this document represents:

- An **individually executable test case**
- Directly mapped to a Postman request
- Or a single iteration in Newman data-driven execution

This document does not describe test strategy or prioritization.  
Its sole purpose is to **explicitly enumerate everything that has been tested**  
and serve as the foundation for later analysis and test plan reduction.

---

### How to Read This Document

- Test cases are grouped by API domain (Products / Carts / Users / Auth)
- Each Test Item (ITEM-XXX) consistently includes:
  - Contract testing
  - Behavior testing
  - Error handling testing
- Test results and observations derived from this list are documented in:
  - `03_result_analysis_and_grouping.md`
  - `04_summary_report.md`



| Test Case ID   | Test Item ID   | Type        | API                               | Variant        | Test Objective                                  |
| -------------- | -------------- | ----------- | ------------------------------    | -------------- | -----------------------------------------       |
| TC-001         | P-ITEM-001     | Contract    | GET /products                     | -              | Validate response schema and data types         |
| TC-002         | P-ITEM-001     | Behavior    | GET /products                     | -              | Verify list returns array of products           |
| TC-003         | P-ITEM-001     | Error       | GET /products                     | -              | Verify invalid method or header handling        |
| TC-004         | P-ITEM-002     | Contract    | POST /products                    | -              | Validate response structure for created product |
| TC-005         | P-ITEM-002     | Behavior    | POST /products                    | -              | Verify product creation behavior                |
| TC-006         | P-ITEM-002     | Error       | POST /products                    | -              | Verify missing or invalid body handling         |
| TC-007         | P-ITEM-003     | Contract    | GET /products/{id}                | -              | Validate single product schema                  |
| TC-008         | P-ITEM-003     | Behavior    | GET /products/{id}                | -              | Verify correct product returned                 |
| TC-009         | P-ITEM-003     | Error       | GET /products/{id}                | -              | Verify invalid or non-existent id handling      |
| TC-010         | P-ITEM-004     | Contract    | PUT /products/{id}                | -              | Validate response structure for update          |
| TC-011         | P-ITEM-004     | Behavior    | PUT /products/{id}                | -              | Verify update behavior                          |
| TC-012         | P-ITEM-004     | Error       | PUT /products/{id}                | -              | Verify invalid update handling                  |
| TC-013         | P-ITEM-005     | Contract    | DELETE /products/{id}             | -              | Validate delete response structure              |
| TC-014         | P-ITEM-005     | Behavior    | DELETE /products/{id}             | -              | Verify delete behavior                          |
| TC-015         | P-ITEM-005     | Error       | DELETE /products/{id}             | -              | Verify invalid delete handling                  |
| TC-016         | P-ITEM-006     | Contract    | GET /products                     | limit          | Validate schema with limit applied              |
| TC-017         | P-ITEM-006     | Behavior    | GET /products                     | limit          | Verify number of returned items                 |
| TC-018         | P-ITEM-006     | Error       | GET /products                     | limit          | Verify invalid limit handling                   |
| TC-019         | P-ITEM-007     | Contract    | GET /products                     | sort           | Validate schema with sorting                    |
| TC-020         | P-ITEM-007     | Behavior    | GET /products                     | sort           | Verify sorting order                            |
| TC-021         | P-ITEM-007     | Error       | GET /products                     | sort           | Verify invalid sort value handling              |
| TC-022         | P-ITEM-008     | Contract    | GET /products/categories          | -              | Validate category list schema                   |
| TC-023         | P-ITEM-008     | Behavior    | GET /products/categories          | -              | Verify category list content                    |
| TC-024         | P-ITEM-008     | Error       | GET /products/categories          | -              | Verify unexpected error handling                |
| TC-025         | P-ITEM-009     | Contract    | GET /products/category/{category} | -              | Validate category product schema                |
| TC-026         | P-ITEM-009     | Behavior    | GET /products/category/{category} | -              | Verify products filtered by category            |
| TC-027         | P-ITEM-009     | Error       | GET /products/category/{category} | -              | Verify invalid category handling                |
| TC-028         | C-ITEM-001     | Contract    | GET /carts                        | -              | Validate cart list schema                       |
| TC-029         | C-ITEM-001     | Behavior    | GET /carts                        | -              | Verify cart list behavior                       |
| TC-030         | C-ITEM-001     | Error       | GET /carts                        | -              | Verify error handling                           |
| TC-031         | C-ITEM-002     | Contract    | POST /carts                       | -              | Validate cart creation response                 |
| TC-032         | C-ITEM-002     | Behavior    | POST /carts                       | -              | Verify cart creation behavior                   |
| TC-033         | C-ITEM-002     | Error       | POST /carts                       | -              | Verify invalid cart body handling               |
| TC-034         | C-ITEM-003     | Contract    | GET /carts/{id}                   | -              | Validate single cart schema                     |
| TC-035         | C-ITEM-003     | Behavior    | GET /carts/{id}                   | -              | Verify cart retrieval                           |
| TC-036         | C-ITEM-003     | Error       | GET /carts/{id}                   | -              | Verify invalid cart id handling                 |
| TC-037         | C-ITEM-004     | Contract    | PUT /carts/{id}                   | -              | Validate cart update response                   |
| TC-038         | C-ITEM-004     | Behavior    | PUT /carts/{id}                   | -              | Verify cart update behavior                     |
| TC-039         | C-ITEM-004     | Error       | PUT /carts/{id}                   | -              | Verify invalid update handling                  |
| TC-040         | C-ITEM-005     | Contract    | DELETE /carts/{id}                | -              | Validate cart delete response                   |
| TC-041         | C-ITEM-005     | Behavior    | DELETE /carts/{id}                | -              | Verify cart delete behavior                     |
| TC-042         | C-ITEM-005     | Error       | DELETE /carts/{id}                | -              | Verify invalid delete handling                  |
| TC-043         | C-ITEM-006     | Contract    | GET /carts                        | limit          | Validate schema with limit                      |
| TC-044         | C-ITEM-006     | Behavior    | GET /carts                        | limit          | Verify limited cart list                        |
| TC-045         | C-ITEM-006     | Error       | GET /carts                        | limit          | Verify invalid limit handling                   |
| TC-046         | C-ITEM-007     | Contract    | GET /carts                        | sort           | Validate schema with sort                       |
| TC-047         | C-ITEM-007     | Behavior    | GET /carts                        | sort           | Verify sort order                               |
| TC-048         | C-ITEM-007     | Error       | GET /carts                        | sort           | Verify invalid sort handling                    |
| TC-049         | C-ITEM-008     | Contract    | GET /carts/user/{userId}          | -              | Validate user cart schema                       |
| TC-050         | C-ITEM-008     | Behavior    | GET /carts/user/{userId}          | -              | Verify carts filtered by user                   |
| TC-051         | C-ITEM-008     | Error       | GET /carts/user/{userId}          | -              | Verify invalid userId handling                  |
| TC-052         | C-ITEM-009     | Contract    | GET /carts                        | date-range     | Validate schema with date filter                |
| TC-053         | C-ITEM-009     | Behavior    | GET /carts                        | date-range     | Verify date range filtering                     |
| TC-054         | C-ITEM-009     | Error       | GET /carts                        | date-range     | Verify invalid date handling                    |
| TC-055         | U-ITEM-001     | Contract    | GET /users                        | -              | Validate user list schema                       |
| TC-056         | U-ITEM-001     | Behavior    | GET /users                        | -              | Verify user list behavior                       |
| TC-057         | U-ITEM-001     | Error       | GET /users                        | -              | Verify error handling                           |
| TC-058         | U-ITEM-002     | Contract    | POST /users                       | -              | Validate user creation response                 |
| TC-059         | U-ITEM-002     | Behavior    | POST /users                       | -              | Verify user creation behavior                   |
| TC-060         | U-ITEM-002     | Error       | POST /users                       | -              | Verify invalid user body handling               |
| TC-061         | U-ITEM-003     | Contract    | GET /users/{id}                   | -              | Validate single user schema                     |
| TC-062         | U-ITEM-003     | Behavior    | GET /users/{id}                   | -              | Verify user retrieval                           |
| TC-063         | U-ITEM-003     | Error       | GET /users/{id}                   | -              | Verify invalid user id handling                 |
| TC-064         | U-ITEM-004     | Contract    | PUT /users/{id}                   | -              | Validate user update response                   |
| TC-065         | U-ITEM-004     | Behavior    | PUT /users/{id}                   | -              | Verify user update behavior                     |
| TC-066         | U-ITEM-004     | Error       | PUT /users/{id}                   | -              | Verify invalid update handling                  |
| TC-067         | U-ITEM-005     | Contract    | DELETE /users/{id}                | -              | Validate user delete response                   |
| TC-068         | U-ITEM-005     | Behavior    | DELETE /users/{id}                | -              | Verify user delete behavior                     |
| TC-069         | U-ITEM-005     | Error       | DELETE /users/{id}                | -              | Verify invalid delete handling                  |
| TC-070         | U-ITEM-006     | Contract    | GET /users                        | limit          | Validate schema with limit                      |
| TC-071         | U-ITEM-006     | Behavior    | GET /users                        | limit          | Verify limited user list                        |
| TC-072         | U-ITEM-006     | Error       | GET /users                        | limit          | Verify invalid limit handling                   |
| TC-073         | U-ITEM-007     | Contract    | GET /users                        | sort           | Validate schema with sort                       |
| TC-074         | U-ITEM-007     | Behavior    | GET /users                        | sort           | Verify sort order                               |
| TC-075         | U-ITEM-007     | Error       | GET /users                        | sort           | Verify invalid sort handling                    |
| TC-076         | A-ITEM-001     | Contract    | POST /auth/login                  | -              | Validate login response schema                  |
| TC-077         | A-ITEM-001     | Behavior    | POST /auth/login                  | -              | Verify successful login behavior                |
| TC-078         | A-ITEM-001     | Error       | POST /auth/login                  | -              | Verify invalid credential handling              |


===

EXECUTION_PLAN
- Collection 建立與執行總順序表（Execution Order Overview）

Phase 1 — Products（TC-001 ～ TC-027）

| Phase | Item Order | Test Item ID | Test Case ID Range | Endpoint / Feature                | Notes              |
| ----: | ---------: | ------------ | ------------------ | --------------------------------- | ------------------ |
|    P1 |        P-1 | P-ITEM-001   | TC-001 ~ TC-003    | GET /products                     | baseline list      |
|    P1 |        P-2 | P-ITEM-002   | TC-004 ~ TC-006    | POST /products                    | create product     |
|    P1 |        P-3 | P-ITEM-003   | TC-007 ~ TC-009    | GET /products/{id}                | single item        |
|    P1 |        P-4 | P-ITEM-004   | TC-010 ~ TC-012    | PUT /products/{id}                | update             |
|    P1 |        P-5 | P-ITEM-005   | TC-013 ~ TC-015    | DELETE /products/{id}             | delete             |
|    P1 |        P-6 | P-ITEM-006   | TC-016 ~ TC-018    | GET /products?limit={n}           | pagination         |
|    P1 |        P-7 | P-ITEM-007   | TC-019 ~ TC-021    | GET /products?sort={asc|desc}     | sorting            |
|    P1 |        P-8 | P-ITEM-008   | TC-022 ~ TC-024    | GET /products/categories          | category list      |
|    P1 |        P-9 | P-ITEM-009   | TC-025 ~ TC-027    | GET /products/category/{category} | filter by category |


Phase 2 — Carts（TC-028 ～ TC-054）

| Phase | Item Order | Test Item ID | Test Case ID Range | Endpoint / Feature           | Notes         |
| ----: | ---------: | ------------ | ------------------ | ---------------------------- | ------------- |
|    P2 |        C-1 | C-ITEM-001   | TC-028 ~ TC-030    | GET /carts                   | baseline list |
|    P2 |        C-2 | C-ITEM-002   | TC-031 ~ TC-033    | POST /carts                  | create cart   |
|    P2 |        C-3 | C-ITEM-003   | TC-034 ~ TC-036    | GET /carts/{id}              | single cart   |
|    P2 |        C-4 | C-ITEM-004   | TC-037 ~ TC-039    | PUT /carts/{id}              | update        |
|    P2 |        C-5 | C-ITEM-005   | TC-040 ~ TC-042    | DELETE /carts/{id}           | delete        |
|    P2 |        C-6 | C-ITEM-006   | TC-043 ~ TC-045    | GET /carts?limit={n}         | pagination    |
|    P2 |        C-7 | C-ITEM-007   | TC-046 ~ TC-048    | GET /carts?sort={asc|desc}   | sorting       |
|    P2 |        C-8 | C-ITEM-008   | TC-049 ~ TC-051    | GET /carts?startdate&enddate | date range    |
|    P2 |        C-9 | C-ITEM-009   | TC-052 ~ TC-054    | GET /carts/user/{userId}     | carts by user |


Phase 3 — Users（TC-055 ～ TC-075）

| Phase | Item Order | Test Item ID | Test Case ID Range | Endpoint / Feature         | Notes         |
| ----: | ---------: | ------------ | ------------------ | -------------------------- | ------------- |
|    P3 |        U-1 | U-ITEM-001   | TC-055 ~ TC-057    | GET /users                 | baseline list |
|    P3 |        U-2 | U-ITEM-002   | TC-058 ~ TC-060    | POST /users                | create user   |
|    P3 |        U-3 | U-ITEM-003   | TC-061 ~ TC-063    | GET /users/{id}            | single user   |
|    P3 |        U-4 | U-ITEM-004   | TC-064 ~ TC-066    | PUT /users/{id}            | update        |
|    P3 |        U-5 | U-ITEM-005   | TC-067 ~ TC-069    | DELETE /users/{id}         | delete        |
|    P3 |        U-6 | U-ITEM-006   | TC-070 ~ TC-072    | GET /users?limit={n}       | pagination    |
|    P3 |        U-7 | U-ITEM-007   | TC-073 ~ TC-075    | GET /users?sort={asc|desc} | sorting       |


Phase 4 — Auth（TC-076 ～ TC-078）

| Phase | Item Order | Test Item ID | Test Case ID Range | Endpoint / Feature | Notes     |
| ----: | ---------: | ------------ | ------------------ | ------------------ | --------- |
|    P4 |        A-1 | A-ITEM-001   | TC-076 ~ TC-078    | POST /auth/login   | auth flow |


