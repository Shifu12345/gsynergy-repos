# Refund Data (`rfnd_data`) Repository

## Overview
The `rfnd_data` folder contains processed and aggregated data tables derived from retail sales transactions. These tables are optimized for analytical queries and reporting.

## Key Table
### `mview_weekly_sales`
This table stores aggregated weekly sales data by store, SKU, and pricing substate. It is derived from the `fact_sales_performance` table with relevant transformations and rounding applied.

### Data Processing Logic
- **Source Data:** `processed_data.fact_sales_performance`
- **Transformations:**
  - Grouped by `store_id`, `sku_id`, `fsclwk_id`, `price_substate_id`, and `prod_type`
  - Aggregated sum of `sales_units`, `sales_dollars`, and `discount_dollars`
  - Rounded numeric columns to 2 decimal places for consistency
- **Storage:** Written as an overwrite mode table in `rfnd_data.mview_weekly_sales`

## Usage
To regenerate the `mview_weekly_sales` table, run the aggregation script in Databricks:
```python
mview_weekly_sales.write.mode("overwrite").saveAsTable("rfnd_data.mview_weekly_sales")
```

## Contributors
- **Shivadatt** – Data Engineer
