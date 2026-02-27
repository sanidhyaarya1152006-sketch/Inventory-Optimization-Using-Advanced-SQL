 Inventory Optimization Using Advanced SQL Analytics

A scalable ETL + Analytics pipeline in MySQL designed to solve real-world retail inventory inefficiencies through structured data modeling, validation, and advanced SQL analysis.

 Project Overview

Retail businesses often struggle with:

Frequent stockouts of high-demand products

Overstocking of slow-moving SKUs

High holding costs

Reactive inventory planning

Lack of real-time KPI visibility

This project builds a layered SQL data architecture to transform raw transactional data into actionable inventory intelligence.

 Architecture

The solution follows a 3-layer Medallion Architecture approach:

Raw Data → Bronze Layer → Silver Layer → Analytical Layer
🔹 Bronze Layer (Raw Ingestion)

Stores raw CSV data

Uses LOAD DATA INFILE

Designed for scalable ingestion

Minimal transformation

Files:

bronze_ddl.sql

proc_load_bronze.sql

🔸 Silver Layer (Data Cleaning & Normalization)

Structured relational schema

Referential integrity with foreign keys

Composite key design

Data standardization & deduplication

Tables:

Products

Stores

Inventory

Sales

Orders

Weather

Forecasts

Files:

silver_ddl.sql

proc_load_silver.sql

 Data Quality Checks

Deduplication using ROW_NUMBER() and CTEs

String trimming & standardization

Unique ID validation

Date consistency checks

Removal of duplicate weather entries

Ensures reliable downstream analytics.

 Analytical Layer (Business Intelligence)

Located in the analysis/ folder.

1) Stock Summary

Regional & store-level rollups

Understocked & overstocked detection

2️) Low Inventory Detection

7-day reorder threshold

Based on 30-day historical demand

3️) Reorder Point Calculation
Reorder Point = Avg Daily Demand × 7

Optional safety buffer supported.

4️) Inventory Turnover Analysis

Monthly turnover ratio

Classification: High / Moderate / Low

5️) KPI Summary

Stockout rate

Inventory aging

Average stock levels

🛠 Tech Stack

MySQL

Advanced SQL (CTEs, Window Functions, Aggregations)

Relational Data Modeling

ETL Pipeline Design

 Project Structure
project/
│
├── bronze_ddl.sql
├── proc_load_bronze.sql
│
├── silver_ddl.sql
├── proc_load_silver.sql
│
├── analysis/
│   ├── stock_summary.sql
│   ├── low_inventory.sql
│   ├── reorder_point.sql
│   ├── turnover_ratio.sql
│   └── kpi_summary.sql
│
└── README.md
 Business Impact

✔ Reduced stockouts
✔ Lower holding costs
✔ Data-driven reorder decisions
✔ Improved working capital utilization
✔ Scalable foundation for BI dashboards

 Key Learnings

Designing layered data architecture

Building production-style SQL ETL pipelines

Writing modular analytical SQL

Implementing real-world inventory KPIs

Data validation before analytics


 Future Improvements

Add safety stock calculation using demand variability

Integrate lead-time forecasting

Connect to BI tools (Power BI / Metabase)

Automate daily pipeline scheduling

Connect to BI tools (Power BI / Metabase)

Automate daily pipeline scheduling
