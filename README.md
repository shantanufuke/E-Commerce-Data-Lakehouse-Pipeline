# 🛒 E-Commerce Data Lakehouse Pipeline

An end-to-end data engineering pipeline for processing e-commerce data using **Azure Data Factory**, **Azure Data Lake Gen2**, and **Azure Databricks** with a **medallion architecture** approach (Bronze → Silver → Gold).

![image](https://github.com/user-attachments/assets/1b45adb8-13b6-40c9-a280-c7ad6c69d37a)

## 🚀 Project Workflow

1. **Raw Data Ingestion to Azure Data Lake**
   - E-commerce data files in CSV format are stored in the `raw/` folder of **Azure Data Lake Gen2**.
   - **Azure Data Factory (ADF)** pipelines ingest and stage the files.
   - Files are converted to **Parquet format** and moved to a new container.
   - An **event-based trigger** initiates the workflow automatically upon file arrival.

2. **Transformation with Azure Databricks**
   - **Databricks notebooks** process staged files from the Bronze layer.
   - Data is cleaned, deduplicated, typecast, and enriched using **PySpark**.
   - Transformed data is written to **Delta tables** in Silver and Gold layers using the **Medallion Architecture**.
   - Files are categorized as **processed** or **unprocessed** for traceability.

3. **Analytics & Visualization**
   - Gold layer data is queried using **Databricks SQL Editor**.
   - Dashboards are created to analyze various e-commerce insights such as:
     - Sales performance
     - Customer behavior
     - Product trends

## 🧰 Tech Stack

- Azure Data Lake Gen2  
- Azure Data Factory  
- Azure Databricks  
- PySpark  
- Delta Lake  
- SQL  
- Parquet  
- Databricks SQL  
- GitHub

