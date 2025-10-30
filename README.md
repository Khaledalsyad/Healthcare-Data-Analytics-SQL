# Healthcare Data Analytics SQL Project

This project focuses on data cleaning, transformation, and exploratory analysis of healthcare-related datasets using **Microsoft SQL Server**.  
It includes datasets about **Egyptian doctors**, **patients**, and **cancer cases** (UAE dataset).

---

## 📊 Project Overview

The project is divided into two main phases:

1. **Data Preparation and Cleaning (Bronze → Silver Layer)**
2. **Descriptive and Analytical SQL Queries**

The goal is to extract insights about:
- Doctor specialization, fees, and ratings.
- Cancer type distribution and recovery rates.
- Patient transportation, distance, and treatment outcomes.

---

## 🧱 1. Data Preparation (ETL Phase)

### Files Used
- `Egyptian Doctors Data.csv`
- `pationt_data.csv`
- `cancer_dataset_uae.csv`

### Steps
- Create base tables in the `dbo` schema.
- Load raw CSV data using `BULK INSERT`.
- Create cleaned tables under the `silver` schema.
- Apply cleaning operations:
  - Remove unwanted characters like `"EGP"`, `"From"`, `"View(s)"`.
  - Trim whitespace and fix inconsistent text.
  - Handle null or missing values.
  - Normalize columns like `waiting_time`, `rate_count`, and `doctor_views`.

Example:
```sql
REPLACE(fees, 'EGP', '') AS fees
TRIM(specialization) AS specialization
