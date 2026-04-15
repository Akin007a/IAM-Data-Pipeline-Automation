### Overview

This project demonstrates an end-to-end data pipeline for processing Identity & Access Management (IAM) data.

It simulates how organisations collect, transform, and analyse access control data to support security monitoring and reporting.

### Business Problem

IAM data is often:

- Stored across multiple systems
- Inconsistent and unstructured
- Difficult to analyse in real-time

This leads to:

- Delayed risk detection
- Inefficient reporting
- Limited visibility into access issues

### Solution

Developed an automated data pipeline that:

- Ingests IAM-related data
- Cleans and transforms it
- Outputs structured datasets for reporting
- Pipeline Architecture

### Source Data → ETL (Python/SQL) → Processed Data → Reporting Layer

### Key Features

🔄 Automated data ingestion
🧹 Data cleaning & validation
📊 KPI generation (risk, access usage)
⚡ Scalable workflow design
📁 Output-ready datasets for dashboards

Tech Stack
Python (data processing)
SQL (data transformation)
Optional: Airflow (workflow orchestration)
  
### Key Metrics Generated

1. Access risk levels
2. Inactive accounts
3. Privileged access usage
4. Access frequency trends

### Business Impact

- Enables continuous monitoring of IAM data
- Improves reporting efficiency
- Supports data-driven security decisions

### How to Run

1. Run Python script for data ingestion
2. Execute SQL transformations
3. Output processed dataset
4. Connect to dashboard/reporting tool

### Author Note

This project demonstrates how data engineering and analytics can be combined to support IAM reporting and cybersecurity operations.

  ⚙️ PROJECT 2: PYTHON PIPELINE (STEP-BY-STEP)
    
1. PIPELINE FLOW
Raw CSV → Python Cleaning → SQL Load → KPI Tables → Dashboard

2. PYTHON SCRIPT (CORE LOGIC)
import pandas as pd

## Load data
users = pd.read_csv('users.csv')
logs = pd.read_csv('access_logs.csv')

## Clean data
users['last_login_date'] = pd.to_datetime(users['last_login_date'])

## Create inactive flag
users['inactive_flag'] = users['last_login_date'] < (pd.Timestamp.today() - pd.Timedelta(days=90))

## Aggregate KPI
inactive_count = users['inactive_flag'].sum()

print(f"Inactive Users: {inactive_count}")
    
3. AUTOMATION IDEA (OPTIONAL)
Schedule script daily
Output:
Clean dataset
KPI summary file
