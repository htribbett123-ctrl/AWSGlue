# AWS Glue → S3 → Redshift ETL Pipeline

<p align="center">

  <!-- Python -->
  <img src="https://img.shields.io/badge/Python-3.9-blue?style=for-the-badge" />

  <!-- AWS Glue -->
  <img src="https://img.shields.io/badge/AWS%20Glue-ETL-orange?style=for-the-badge&logo=amazon-aws" />

  <!-- AWS S3 -->
  <img src="https://img.shields.io/badge/AWS%20S3-Storage-yellow?style=for-the-badge&logo=amazon-aws" />

  <!-- AWS Redshift -->
  <img src="https://img.shields.io/badge/AWS%20Redshift-Data%20Warehouse-red?style=for-the-badge&logo=amazon-aws" />

  <!-- License -->
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" />

  <!-- Repo Size -->
  <img src="https://img.shields.io/github/repo-size/YOUR_GITHUB_USERNAME/aws-glue-s3-redshift-etl?style=for-the-badge" />

  <!-- Last Commit -->
  <img src="https://img.shields.io/github/last-commit/YOUR_GITHUB_USERNAME/aws-glue-s3-redshift-etl?style=for-the-badge" />

</p>


A fully automated ETL pipeline that ingests raw CSV data from S3, processes it using AWS Glue, applies data quality rules, stores cleaned data back into S3, and loads it into Amazon Redshift for analytics.

---

## 🚀 Architecture Overview

S3 (Raw) → Glue Crawler → Glue ETL → S3 (Processed) → Redshift COPY → Analytics

---

## 📂 Repository Structure

```text
aws-glue-s3-redshift-etl/
├── glue/
├── redshift/
├── s3/
├── iam/
├── docs/
└── data/
```




---

## 🧩 Components

### **S3 Buckets**
- `raw/` — stores unprocessed CSV files  
- `processed/` — stores cleaned output from Glue ETL  

### **AWS Glue**
- Crawler to infer schema  
- ETL job to clean + transform data  
- Data Quality job to validate fields  

### **Amazon Redshift**
- Table creation  
- COPY command to load processed data  
- Validation queries  

---

## 🧪 Data Quality Rules
```text
IsComplete "customer_id"
IsComplete "signup_date"
Completeness "full_name" >= 0.6
Completeness "age" >= 0.6
Completeness "country" >= 0.6
ColumnValues "age" between 0 and 120
```

---

## 📜 ETL Script

Located in:

glue/etl_job.py


---

## 🧾 SQL Scripts

redshift/create_table.sql
redshift/validation_queries.sql


---

## 🎯 Purpose

This project demonstrates a complete, production‑ready AWS ETL pipeline suitable for:

- Data engineering portfolios  
- Real-world ETL automation  
- Redshift analytics pipelines  
- Data quality enforcement  

---


