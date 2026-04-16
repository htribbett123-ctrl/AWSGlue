# AWS Glue → S3 → Redshift ETL Pipeline

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

IsComplete "customer_id"
IsComplete "signup_date"
Completeness "full_name" >= 0.6
Completeness "age" >= 0.6
Completeness "country" >= 0.6
ColumnValues "age" between 0 and 120


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


