# 🛒 E-Commerce Data Lakehouse Pipeline

![image](https://github.com/user-attachments/assets/240d0d9f-e137-41cd-adea-08ac9cbd3d69)

Built an end-to-end data pipeline using Azure and Databricks to process e-commerce data following the **Medallion Architecture**.

### 📦 **Data Ingestion**
- Stored raw CSV files in **Azure Data Lake Gen2**.
- Created automated pipelines using **Azure Data Factory (ADF)** to convert these files into **Parquet format** and move them to a separate container.
- Configured **event-based triggers** to automatically start the workflow when new files arrived.

### 🔄 **Transformation & Storage**
- Used **Azure Databricks (PySpark)** to implement **Bronze, Silver, and Gold layers** using **Delta Lake**.
- Performed data cleaning, deduplication, and enrichment.
- Generated a unified Gold table for reporting and analytics.
- All **Databricks notebooks** were auto-triggered on new file arrivals.

### 📑 **Data Quality & Processing**
- Labeled files as **processed** or **unprocessed** to maintain data traceability and pipeline health.

### 📊 **Analysis & Visualization**
- Queried the Gold layer using **Databricks SQL Editor**.

### 🧰 Tech Stack

**Azure Data Lake Gen2** · **Azure Data Factory** · **Azure Databricks** · **PySpark** · **Delta Lake** · **SQL** · **Parquet** · **GitHub**
