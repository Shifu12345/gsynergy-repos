# Processed Data

## Overview  
This directory contains Jupyter/Databricks notebooks that define the logic for creating and updating key dimension and fact tables used in the **retail sales analytics pipeline**. These tables store **processed and structured** data for analysis and reporting.  

## Table Descriptions  

### 1️⃣ **dim_date**  
- A **date dimension table** with a continuous range from **January 1, 2016, to December 31, 2024**.  
- Includes attributes such as day, week, month, quarter, and year for easy time-based analysis.  

### 2️⃣ **dim_hldy**  
- A **holiday dimension table** that tags each date with **holiday labels** (e.g., New Year’s Day, Black Friday).  
- Used for **seasonality analysis** and sales forecasting.  

### 3️⃣ **dim_time_hldy**  
- Combines `dim_date` with `dim_hldy` to **tag each date with its respective holiday information**.  
- Covers the period from **January 1, 2016, to December 31, 2024**.  

### 4️⃣ **dim_str_location**  
- A **store location dimension table** containing **store metadata** such as store ID, name, city, state, and region.  
- Ensures standardization and **deduplication of store location data**.  

### 5️⃣ **fact_holiday_sales**  
- A **fact table capturing sales performance during holiday periods**.  
- Includes **aggregated sales volume, revenue, and discount metrics** during holidays.  
- Used for analyzing the impact of holidays on sales trends.  

### 6️⃣ **fact_sales_performance**  
- A **detailed sales transaction fact table** at the store and SKU level.  
- Includes **date, location, SKU, units sold, revenue, and applied discounts**.  
- Supports performance tracking and sales trend analysis.  

## Notebook Contents  

| Notebook | Description |
|----------|------------|
| `processed_data date table creation.ipynb` | Generates `dim_date` table with a date range from 2016-01-01 to 2024-12-31. , Combines `dim_date` with `dim_hldy` for holiday-tagged dates. , Tags holidays to dates in `dim_hldy`. |
| `processed_data str_location table.ipynb` | Processes and cleans store location data for `dim_str_location`. |
| `processed_data holiday_sales.ipynb` | Aggregates sales data for `fact_holiday_sales`. |
| `processed_data sales performance table.ipynb` | Loads and processes transactional sales data for `fact_sales_performance`. |

## Execution  
To execute the notebooks, follow these steps in **Azure Databricks** :  

```bash
# Run dim_date, holiday mapping, holiday-tagged time dimension generation
python notebooks/`processed_data date table creation.ipynb  

# Process store locations
python notebooks/processed_data str_location table.ipynb

# Aggregate holiday sales data
python notebooks/processed_data holiday_sales.ipynb 

# Process sales transactions
python notebooks/processed_data sales performance table.ipynb 
```

## Usage  
- These tables support **business intelligence (BI) reporting**, **sales forecasting**, and **trend analysis**.  
- Processed tables are stored in Hivemetastore of Databricks.  

