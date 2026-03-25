# Sql-Data_warehouse-Project
# 📊 Data Warehouse Project (Bronze → Silver → Gold)

## 🚀 Project Overview

This project demonstrates an **end-to-end Data Warehouse pipeline** built using **MySQL**.
It follows a **3-layer architecture** (Bronze, Silver, Gold) and transforms raw data into a **Star Schema** for analytics and reporting.

---

## 🏗️ Architecture

```
Raw Data (CSV)
      ↓
Bronze Layer (Raw Tables)
      ↓
Silver Layer (Cleaned + Transformed)
      ↓
Gold Layer (Star Schema Views)
      
```

---

## 🗂️ Database Structure

### 🥉 Bronze Layer (Raw Data)

* `bronze_cust_info`
* `bronze_prd_info`
* `bronze_sales_details`
* `bronze_cust_az12`
* `bronze_loc_a101`
* `bronze_px_cat`

📌 Stores raw CSV data without transformation

---

### 🥈 Silver Layer (Processed Data)

* `silver_customers`
* `silver_products`
* `silver_sales`
* `silver_category`

📌 Transformations applied:

* Data cleaning (TRIM, NULL handling)
* Gender standardization (Male/Female)
* Date conversion
* Price correction
* Deduplication using `ROW_NUMBER()`
* **SCD Type 2** on product table

---

### 🥇 Gold Layer (Star Schema)

* `fact_sales`
* `dim_customers`
* `dim_products`

📌 Designed for analytics and reporting

---

## ⭐ Star Schema Design

```
        dim_customers
              |
              |
dim_products —— fact_sales
```

### Fact Table:

* `fact_sales`

  * order_number
  * customer_key
  * product_key
  * quantity
  * price
  * sales

### Dimension Tables:

* `dim_customers` (customer details)
* `dim_products` (product + category info)

---

## 🔄 ETL Process

### 1️⃣ Bronze Layer

* Data loaded from CSV using `LOAD DATA INFILE`

### 2️⃣ Silver Layer

* Data cleaning & transformation
* Duplicate removal
* Business logic applied

### 3️⃣ Gold Layer

* Created views
* Generated surrogate keys
* Built star schema

---

## 🔥 Key Features

* ✅ Layered Architecture (Bronze, Silver, Gold)
* ✅ Data Cleaning & Standardization
* ✅ Deduplication using Window Functions
* ✅ SCD Type 2 Implementation
* ✅ Star Schema Modeling
  

---



## 📌 Conclusion

This project simulates a **real-world data engineering workflow**

---

## 👨‍💻 Author

**Hritik Raj**

---

