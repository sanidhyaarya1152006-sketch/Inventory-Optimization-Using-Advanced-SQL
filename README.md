#  Inventory Optimization Using Advanced SQL Analytics

A production-style **ETL + Analytics pipeline in MySQL** that transforms raw retail inventory data into actionable business insights.

This project solves real-world inventory problems like stockouts, overstocking, and reactive replenishment using structured data modeling and advanced SQL analytics.

---

##  Problem Statement

Retail businesses commonly face:

-  Frequent stockouts of high-demand products  
-  Overstocking of slow-moving SKUs  
-  High inventory holding costs  
-  Reactive (non-predictive) replenishment  
-  Limited SKU-level visibility  

This project builds a scalable SQL architecture to address these inefficiencies.

---

##  Architecture Overview

The solution follows a 3-layer Medallion Architecture:

Raw Data → Bronze Layer → Silver Layer → Analytics Layer

---

##  Bronze Layer – Raw Data Ingestion

**Purpose:** Store and ingest raw CSV data efficiently.

- Bulk loading using `LOAD DATA INFILE`
- Minimal transformation
- Designed for scalability

**Files:**
- `bronze_ddl.sql`
- `proc_load_bronze.sql`

---

##  Silver Layer – Data Cleaning & Normalization

**Purpose:** Transform raw data into a clean relational schema.

Features:
- Referential integrity with foreign keys
- Composite keys
- Deduplication using `ROW_NUMBER()`
- Standardized string fields
- Date validation checks

**Core Tables:**
- Products  
- Stores  
- Inventory  
- Sales  
- Orders  
- Weather  
- Forecasts  

**Files:**
- `silver_ddl.sql`
- `proc_load_silver.sql`

---

##  Analytical Layer – Business Intelligence

Modular SQL scripts generate actionable insights.

###  Stock Summary
- Inventory rollups (total, regional, store-level)
- Detects understocked & overstocked products

###  Low Inventory Detection
- 7-day reorder threshold
- Based on 30-day sales history

###  Reorder Point Calculation

Reorder Point = Average Daily Demand × 7

(Optional safety buffer supported)

###  Inventory Turnover Analysis
- Monthly turnover ratio
- Classification: High / Moderate / Low

###  KPI Summary
- Stockout rate
- Inventory aging
- Average inventory levels

All analytics use:
- CTEs
- Window functions
- Aggregations

---

##  Tech Stack

- MySQL  
- Advanced SQL (CTEs, Window Functions)  
- Relational Data Modeling  
- ETL Pipeline Design  

---

## 📂 Project Structure

```
project/
│
├── bronze_ddl.sql
├── proc_load_bronze.sql
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
```


---

##  Business Impact

✔ Reduced stockouts  
✔ Smarter reorder decisions  
✔ Lower holding costs  
✔ Improved working capital utilization  
✔ Data-driven inventory planning  

---

##  Key Skills Demonstrated

- Layered Data Architecture Design  
- Production-style SQL ETL Pipelines  
- Advanced Analytical SQL  
- Inventory KPI Development  
- Business Problem Translation into Data Solutions  
  

