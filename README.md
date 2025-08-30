# ShopSmart Retail Warehouse (SQL Server)

![DB](https://img.shields.io/badge/DB-Microsoft%20SQL%20Server-CC2927)
![Lang](https://img.shields.io/badge/Language-T--SQL-blue)
![Focus](https://img.shields.io/badge/Focus-Data%20Modeling%20%7C%20Analytics%20Engineering-green)

Portfolio project in **Microsoft SQL Server**: retail **star schema** + **CSV seed** + executive analytics (YoY revenue & margin, channel mix, return drivers, cohort retention, RFM). Built and tested in **SSMS** with screenshot-ready queries.

---

## Why this matters
- Single source of truth for omni-channel sales & returns
- Answers executive questions on **growth, margin, returns, retention, and winners**
- Reproducible setup with CSV seed data and reusable views

---

## Tech Stack
- SQL Server (T-SQL), SSMS
- Mermaid ERD (renders on GitHub)

---

## ERD
```mermaid
erDiagram
  DIM_DATE ||--o{ FACT_SALES : date_key
  DIM_PRODUCT ||--o{ FACT_SALES : product_key
  DIM_CUSTOMER ||--o{ FACT_SALES : customer_key
  DIM_STORE ||--o{ FACT_SALES : store_key
  DIM_PROMO ||--o{ FACT_SALES : promo_key
  DIM_PRODUCT ||--o{ FACT_RETURNS : product_key
  DIM_CUSTOMER ||--o{ FACT_RETURNS : customer_key
  DIM_DATE ||--o{ FACT_RETURNS : date_key
  FACT_SALES ||--o{ FACT_RETURNS : sale_id

