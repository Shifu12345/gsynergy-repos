### Gsynergy Data Warehousing project

## Overview
This project is a data processing pipeline designed to ingest, transform, and load retail sales data into a structured format using Azure Databricks and Azure Blob Storage. The pipeline includes incremental data processing, data quality checks, and optimized transformations.

## Directory Structure
```
/root_directory
|-- rfnd tables
│-- processed data/          # Refined output tables
│-- raw_data/                # Source data files
│-- README.md                # Project documentation
```

## Data Sources
- **Raw Data:** Stored in `raw_data/`, sourced from POS, inventory, and sales systems.
- **Processed Data:** Transformed datasets in `processed_data/`
- **rfnd Data:** Aggrgated data used for reporting

## Key Tables
### 1️⃣ `fact_sales_performance`
- Contains sales transaction details at the store and SKU level.

### 2️⃣ `mview_weekly_sales`
- Aggregates weekly sales by store, SKU, and price substate.

### 3️⃣ `dim_str_location`
- Contains standardized store location details with deduplication and data validation applied.

## Data Quality Checks
Before loading data into the refined schema, the following checks are performed:
✅ **Schema Validation** – Ensures correct data types
✅ **Null Checks** – Identifies missing critical fields
✅ **Duplicate Checks** – Removes duplicate records
✅ **Invalid ID Checks** – Ensures valid `location_id`
✅ **Referential Integrity** – Cross-checks with existing processed data

## Technologies Used
- **Azure Databricks** – For ETL and transformations
- **Azure Blob Storage** – Storing raw and processed data
- **PySpark** – Data processing and transformations
- **Hive Metastore** – Managing table metadata

## Execution Steps
1️⃣ Upload raw data to `raw_data/`
2️⃣ Run ingestion scripts to load data into staging tables
3️⃣ Execute transformation scripts in Databricks
4️⃣ Validate using DQ scripts before loading into refined tables
5️⃣ Store processed data in `processed_data/`


## Contributors
- **Shivadatt** – Data Engineer


