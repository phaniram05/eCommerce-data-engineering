# eCommerce Data Engineering Project

End-to-End Processing of eCommerce data using Azure stack, Databricks, and Spark.

## Overview

This repository demonstrates the implementation of a **Medallion Architecture** for an eCommerce data engineering pipeline. The Medallion Architecture, also known as the **Lakehouse Architecture**, is designed to improve data quality and streamline data processing for analytics and machine learning (ML) use cases. 

The project processes raw eCommerce datasets (e.g., Customers, Orders, Order Line Items, Products, and Promotions) through three distinct layers—**Bronze**, **Silver**, and **Gold**—to produce clean, structured, and business-ready data.

---

## Architecture

![Medallion Architecture](Project%20Architecture.png)

### Medallion Layers:

1. **Bronze Layer (Raw Data)**:
   - Acts as the "landing zone" for raw data.
   - No schema enforcement is applied at this stage.
   - Data is ingested in its raw format (e.g., CSV, JSON, or Parquet).

2. **Silver Layer (Filtered, Cleaned, Augmented)**:
   - Applies schema enforcement and data validation.
   - Cleans and filters the raw data to produce structured datasets.
   - Augments the data with additional transformations.

3. **Gold Layer (Business-Level Aggregates)**:
   - Contains aggregated and business-ready datasets.
   - Supports downstream applications such as Business Intelligence (BI) dashboards and Machine Learning (ML) models.

---

## Data Sources

The pipeline processes the following datasets:
- **Customers**: Customer information such as demographics and preferences.
- **Orders**: Details of customer orders.
- **Order Line Items**: Individual items within orders.
- **Products**: Product catalog details.
- **Promotions**: Information about active promotions and discounts.

---

## Tools & Technologies

This project leverages the following tools and technologies:
- **Delta Lake**: For efficient storage and ACID-compliant transactions across all layers of the architecture.
- **Azure Data Lake Storage (ADLS)**: For cloud-based scalable storage.
- **Parquet**: As the file format for efficient storage and querying of raw data.
- **Databricks**: For processing and transforming data using Apache Spark.

---

## Workflow

1. **Bronze Layer**:
   - Raw data ingestion from source systems into Delta Lake tables.
   - Stored in Parquet format for flexibility.

2. **Silver Layer**:
   - Data cleaning, filtering, and schema enforcement applied to Bronze tables.
   - Transformed datasets are stored as Delta Lake tables.

3. **Gold Layer**:
   - Aggregated business-level metrics are generated from Silver tables.
   - Final datasets are optimized for BI tools or ML pipelines.

---

## Use Cases

1. **Business Intelligence (BI)**:
   - Generate dashboards for tracking sales performance, customer behavior, product trends, etc.

2. **Machine Learning (ML)**:
   - Build predictive models using clean, structured data from the Gold layer.