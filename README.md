# 🛒 E-Commerce Data Lakehouse Pipeline

Built an end-to-end data pipeline on **Azure** to process e-commerce data following the **Medallion Architecture**.

---

## 📦 Data Ingestion

- Raw CSV files are stored in **Azure Data Lake Gen2** (`landing-zone-1`) under separate folders for users, buyers, sellers, and countries.
- Developed **two Azure Data Factory (ADF) pipelines**:
  - One pipeline for user data
  - One pipeline for other entities
- Each pipeline **automatically converts new CSV files to Parquet format** and moves them to a separate container (`landing-zone-2`) for downstream processing.
- **Event-based triggers** in ADF ensure pipelines run automatically when new files arrive.

---

## 🔄 Transformation & Storage

- Used **Azure Databricks (PySpark)** notebooks to implement **Bronze, Silver, and Gold layers** using **Delta Lake** for scalable data transformation and storage.
- Performed data cleaning, deduplication, and basic enrichment.

---

## 🧰 Tech Stack

**Azure Data Lake Gen2** · **Azure Data Factory** · **Azure Databricks** · **PySpark** · **Delta Lake** · **Parquet** · **SQL** · **GitHub**

---
