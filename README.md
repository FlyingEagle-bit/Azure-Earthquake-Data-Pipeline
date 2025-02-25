# Azure-Earthquake-Data-Pipeline
This repository contains an automated pipeline for collecting, processing, and delivering up-to-date earthquake data. Designed for government agencies, research institutions, and insurance companies, this solution ensures stakeholders receive timely and structured seismic event information

**🌍 Earthquake Data Pipeline – Architecture Overview**  

This pipeline leverages **Azure’s powerful data engineering tools** to ensure **scalability, reliability, and efficiency** in handling seismic event data.  

### 🏗️ **Architecture Overview**  
🔹 **Data Ingestion:** Azure Data Factory orchestrates the **daily** ingestion of earthquake data from the **USGS Earthquake API**.  
🔹 **Data Processing:** Databricks transforms raw data into structured **bronze, silver, and gold** tiers.  
🔹 **Data Storage:** Azure Data Lake Storage acts as the backbone for managing data at different processing stages.  
🔹 **Data Analysis:** Synapse Analytics enables **efficient querying and aggregation** for reporting.  
🔹 **Optional Visualization:** Power BI can be used to create **interactive dashboards** for stakeholders.  

### 📊 **Data Modeling – Medallion Architecture**  
💾 **Bronze Layer:** Raw data stored in **Parquet format** for future reprocessing.  
🔍 **Silver Layer:** Cleaned and normalized data—duplicates removed, missing values handled.  
🏆 **Gold Layer:** Aggregated and enriched data tailored to **business needs** (e.g., adding country codes).  

### 🌐 **Understanding the USGS Earthquake API**  
This API provides **detailed seismic event data** within a specified date range.  
📅 **Start Date:** Dynamically set via **Azure Data Factory** for daily ingestion.  
🔗 **API URL:** [USGS Earthquake API](https://earthquake.usgs.gov/fdsnws/event/1/)  

### 🚀 **Key Benefits**  
✅ **Automation:** Eliminates manual data fetching & processing, reducing operational overhead.  
✅ **Scalability:** Handles **large data volumes** effortlessly using **Azure services**.  
✅ **Actionable Insights:** Provides **stakeholders with ready-to-use** data for informed decision-making.  

This pipeline streamlines earthquake data processing, making critical information **accessible, reliable, and actionable**! 🌍📈

## 🌍 Earthquake Data Pipeline – Configuration Overview

This pipeline is built on Azure’s scalable data engineering tools, ensuring efficient ingestion, processing, and analysis of seismic event data.

## ⚙️ Key Configurations
🔹 Azure Databricks: Standard LTS tier used for processing data in bronze, silver, and gold layers.
🔹 Azure Data Lake Storage: Configured with hierarchical namespaces, with separate containers for each data tier.
🔹 Azure Data Factory (ADF): Orchestrates automated daily data ingestion and pipeline execution.
🔹 Azure Synapse Analytics: Enables serverless SQL querying and structured access via external tables.

## 📊 Data Processing & Storage
💾 Bronze Layer: Raw USGS earthquake data stored in Parquet format for reprocessing.
🔍 Silver Layer: Cleaned and normalized data, removing duplicates and handling missing values.
🏆 Gold Layer: Aggregated and enriched data, including country codes for location-based insights.

## 🔑 Optimization & Performance
✅ Reverse Geocoding: Optimized using precomputed lookup tables instead of Python UDFs for better performance.
✅ Serverless SQL Queries: Synapse OPENROWSET queries enable efficient analysis of Parquet files in Azure Data Lake.
✅ Pipeline Automation: ADF schedules and manages bronze → silver → gold transformations.

This streamlined setup ensures reliable, scalable, and automated earthquake data processing, making seismic insights easier to access and analyze. 🚀
