# End-to-End Retail Sales Lakehouse Pipeline on Databricks

## Project Overview
This project implements a modern data engineering and analytics pipeline utilizing the **Medallion Architecture (Bronze → Silver → Gold)** on Databricks. Using a raw retail transations dataset, I designed a scalable ELT pipeline using **Deltalake SQL** to transform messy data into business ready dimensions, facts and aggregated insights, culminating in an executive performance dashboard.

## Architecture Design 
The pipeline organizes data into three distinct layers to ensure reliability, data quality and fast analytical performance:
1. **Bronze (Raw Landing):** Direct ingestion of raw transactional CSV files into Delta tables without schema modification.
2. **Silver (Cleaned & Modeled):** Deduplication, handling of null values/anomalous records (e.g negative quantities) and restructuring into a highly efficient **Star Schema** ('fact_sales', 'dim_customers', 'dim_products').
3. **Gold (Aggregated Business Layer):** High-level analytical views utilizing window functions and CTEs to compute critical metrics like Month-over-Month (MoM) growth and customer behaviour patterns.

 ## Business Insights Uncovered
* **Revenue Metrics:** Tracked historical sales trends and isolated seasonal revenue spikes.
* **Operational Efficiency:** Identified and segmented order return rates to pinpoint underperforming product categories.
* **Customer Distribution:** Mapping purchase frequencies across different geographic demographics.

## Tech Stack & Tools Used
* **Platform:** Databricks Community/Entreprise Edition
* **Storage & Table Format:** Delta Lake
* **Language:** Advanced SQL (CTEs, Window Funcions, Data Modeling)
* **Version Control:** Git & GitHub integration via Databricks Repos
* **Visualization:** Databricks Lakehouse Dashboards
  
## Repository Structure 
```text
├── assets/
│   └── dashboard_screenshot.png           # Visual preview of the final dashboard
├── notebooks/
│   ├── 01_bronze_ingestion.sql            # Raw file ingestion
│   ├── 02_silver_transformations.sql      # Data cleansing & Star Schema modeling
│   └── 03_gold_aggregations.sql           # Complex business logic & KPIs
└── README.md
