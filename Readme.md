1.Overview
This project implements an end-to-end data pipeline for medical_data using the Medallion Architecture (Bronze, Silver, Gold) in Databricks. The pipeline ingests raw data from AWS S3, processes it through multiple transformation layers, and generates business KPIs.

2.Tech Stack
   Databricks
   PySpark
   Delta Tables
   AWS S3 (External Location)
   GitHub (Version Control)


3.Architecture
The pipeline follows a layered architecture:
       Bronze → Silver → Gold → KPI Result

  Step 1: Git Integration
    1.Connected GitHub repository to Databricks
    2.Created a Git folder inside Databricks workspace

  Step 2: Folder Structure
    project/
          /bronze - Raw Ingestion
          /silver - Cleaned and transformed data 
          /gold   - KPI and business metrics
          /pipeline_master
          /readme
          
  Step 3: Data Ingestion (Bronze Layer)
     1.Connected to AWS S3 using external location
     2.Ingested raw data into Databricks
     3.Stored data in Delta tables

  Step 4: Data Transformation (Silver Layer)
     1.Created separate notebooks for each table:
     2.Naming convention: nb_trm_table_name
     3.Transformations performed:
          |)  Handling null values
          ||) Converting column names to snake_case
          |||)Data cleaning and standardization
  
  Step 5: Data Modeling
     1.Designed Fact and Dimension tables
     2.Ensured proper schema and relationships
  
  Step 6: KPI Layer (Gold)
    1.Created multiple KPI notebooks
    2.Aggregated business-level metrics
    3.Built a unified notebook combining all KPIs
  
  Step 7: Orchestration
    1.Created master notebooks:
        /bronze_master
        /silver_master
        /gold_master
      Each master notebook executes all notebooks in its layer
      Pipeline Flow: bronze_master → silver_master → gold_master
      Used Databricks Workflows (Jobs) to orchestrate execution

  Step 8: Output
     1.Final KPIs showed in SQL query

  Step 9: Optimization
     1.Used Delta format for efficient storage
     2.Structured pipeline for scalability
  
  Step 10: Version Control
    1.Maintained code in GitHub
    2.Followed meaningful commit practices
    
