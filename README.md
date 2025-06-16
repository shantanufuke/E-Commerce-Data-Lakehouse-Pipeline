# 🛒 E-Commerce Data Lakehouse Pipeline

This project demonstrates an end-to-end data lakehouse solution for e-commerce data, implemented using **Azure Data Lake Gen2**, **Azure Data Factory (ADF)**, and **Azure Databricks (PySpark)**.  
It follows the **Medallion Architecture** to enable scalable, reliable, and high-quality analytics.

---

## 📦 Data Ingestion

- **Raw CSV files** for users, buyers, sellers, and countries are ingested into the `landing-zone-1` container in Azure Data Lake Gen2.
- Each entity has its own folder (`users-raw-1`, `buyers-raw-1`, etc.) to organize raw data.
- **Two automated ADF pipelines**:
  - One pipeline for user data
  - One pipeline for buyers, sellers, and countries
- **ADF pipelines** automatically convert new CSVs to **Parquet format** and move them to the `landing-zone-2` container for downstream transformation.
- **Event-based triggers** in ADF ensure pipelines run automatically when new files arrive.

---

## 🔄 Medallion Architecture: Bronze, Silver, Gold Layers

### 🥉 Bronze Layer
- **Purpose:**  
  - Ingests raw Parquet data from the landing zone with minimal processing.
  - Retains data in its most granular form.
  - Provides an auditable, append-only, and traceable raw data layer.
- **Processing:**  
  - Loads raw data into **Delta tables** without heavy transformations.
  - Enables schema evolution and data lineage for raw ingested data.

### 🥈 Silver Layer
- **Purpose:**  
  - Cleans, filters, and applies business rules to the Bronze data.
  - Handles missing values, deduplication, type casting, and basic joins.
- **Processing:**  
  - Transforms Bronze Delta tables into more structured Silver Delta tables.
  - Prepares data for advanced analytics and reporting by unifying, standardizing, and enriching records.

### 🥇 Gold Layer
- **Purpose:**  
  - Aggregates, joins, and curates the data for business consumption and reporting.
  - Creates comprehensive, analytics-ready tables combining multiple dimensions (users, buyers, sellers, countries).
- **Processing:**  
  - Joins Silver tables, adds business logic, and computes metrics.
  - Produces a **unified Gold table**—ideal for dashboards, BI tools, and data science.
  - The notebook provides ready-to-query tables for advanced analytics.

---

## 📑 Output Example

- The final **Gold table** combines user transactions with buyer, seller, and country attributes, making it suitable for reporting, KPI generation, and visualization.

---

## 📊 Data Analysis

- Query the Gold Delta table using **Databricks SQL** or connect Power BI/Tableau for visualization.
- Gold layer tables are ready for direct analytics, minimizing time-to-insight for business users.

---


