# Retail Data Pipeline Project

This project demonstrates the implementation of a retail data pipeline using modern data tools and platforms. It covers end-to-end data ingestion, transformation, quality checks, and reporting using **Apache Airflow**, **DBT**, **Soda**, **Google Cloud Platform (GCP)**, and **Metabase**. The Astro CLI was utilized for Airflow workflow orchestration.

> **Note**: This project was inspired by Marc Lamberti's YouTube video, and the dataset used is sourced from Kaggle: [Online Retail Dataset](https://www.kaggle.com/datasets/tunguz/online-retail).

---

## Project Overview

The pipeline processes a retail dataset by:
- **Ingesting data** from a CSV file to Google Cloud Storage (GCS).
- **Transforming raw data** into a dimensional model using DBT.
- **Validating data quality** using Soda.
- **Generating reports** for business insights.
- **Visualizing results** with Metabase.

---

## Project Organization


```
├── README.md                <- Project documentation.
├── airflow_settings.yaml    <- Airflow configurations for this project.
├── dags                     <- Airflow DAGs for orchestrating workflows.
│   ├── retail.py            <- Main DAG for data ingestion and processing.
├── include                  <- Supporting files and configurations.
│   ├── dataSets             <- Source data files.
│   │   └── online_retail.csv <- Retail dataset used for this project.
│   ├── gcp                  <- GCP service account credentials and configs.
│   │   └── serviceAccount.json <- Service account JSON file for authentication.
│   ├── dbt                  <- DBT project for data transformation.
│   │   ├── models           <- DBT models for data transformations and reports.
│   │   ├── profiles.yml     <- DBT connection configuration for BigQuery.
│   │   └── cosmos_config.py <- DBT integration with Airflow.
│   ├── soda                 <- Soda configurations for data quality checks.
│       ├── checks           <- Data quality check definitions.
│       └── check_function.py <- Python function to execute Soda scans.
├── metabase-data            <- Metabase configurations for dashboards.
├── requirements.txt         <- Python dependencies for this project.
├── Dockerfile               <- Docker configuration for the Airflow environment.
├── docker-compose.override.yml <- Metabase setup for visualization.
└── target                   <- Compiled DBT files.

```
---

## How to Run the Project

1. **Set up the environment**:
   - Add required Python packages: `pip install -r requirements.txt`.
   - Build the Docker image: `astro dev start`.

2. **Run the pipeline**:
   - Launch Airflow: `astro dev start`.
   - Trigger the DAG `retail` from the Airflow UI.

3. **Verify outputs**:
   - Check **BigQuery** for transformed data tables.
   - Inspect **Metabase** dashboards for generated reports.
   - Review **Soda Cloud** for data quality reports.

# Note: I did not attach service account and other downloads those should be added once you download the astro cli and run astro dev start when getting project started. 

---

## Reports and Insights

The pipeline generates:
1. **Customer Invoices**: Total revenue and invoice count per customer country.
2. **Product Sales**: Top-selling products and quantities sold.
3. **Yearly Revenue**: Monthly revenue trends and invoice counts.

These insights help drive strategic decisions for retail business optimization.

---
--------
