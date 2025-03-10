# GSynergy Raw Data

## Overview
The `raw_data` folder contains Databricks notebooks used for setting up, exploring, and creating raw tables in Azure Blob Storage. This serves as the first stage of the data pipeline, where data is ingested and structured before processing.

## Contents

### 1️⃣ `azure blob mount.ipynb`
- Configures **Azure Blob Storage** mounts in Databricks.
- Establishes connectivity between Databricks and the storage account.
- Ensures seamless access to raw data files for further processing.

### 2️⃣ `EDA gsynergy raw.ipynb`
- Performs **Exploratory Data Analysis (EDA)** on raw datasets.
- Identifies missing values, outliers, and data distributions.
- Provides insights into data quality before transformation.

### 3️⃣ `create raw tables.ipynb`
- Creates **raw tables** in Databricks.
- Loads raw data from Azure Blob Storage into a structured format.
- Sets up necessary schemas for downstream processing.

## Execution Steps
1. Open Databricks and run `azure blob mount.ipynb` to set up storage mounts.
2. Execute `EDA gsynergy raw.ipynb` to analyze raw data.
3. Run `create raw tables.ipynb` to create structured raw tables.

## Notes
- Ensure Azure credentials and storage access permissions are configured before running these notebooks.
- Validate the raw data after ingestion to prevent errors in downstream processes.

## Contributors
- **Shivadatt** – Data Engineer
