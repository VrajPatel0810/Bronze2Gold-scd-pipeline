# 🏗️ Data Modeling Pipeline – From Bronze to Gold with SCD

This project demonstrates a **real-world data modeling pipeline** using the **Bronze → Silver → Gold architecture** and implementing both **SCD Type 1 & Type 2**.

---

## 📂 Source Table: `datamodeling.default.source_data`

### Columns:
- `order_id` (INT, Primary Key)  
- `order_date` (DATE)  
- `customer_id` (INT)  
- `customer_name` (STRING)  
- `customer_email` (STRING)  
- `product_id` (INT)  
- `product_name` (STRING)  
- `product_category` (STRING)  
- `quantity` (INT)  
- `unit_price` (DECIMAL)  
- `payment_type` (STRING)  
- `country` (STRING)  
- `last_updated` (DATE)  

---

## 🥉 Bronze Layer
- Ingested raw transactional data as-is.  
- Preserved duplicates and inconsistencies.  
- Stored in `source_data` table.  

## 🥈 Silver Layer
- Applied cleaning and transformations.  
- Removed duplicates, standardized formats (dates, strings).  
- Built intermediate tables ready for dimension modeling.  

## 🥇 Gold Layer
- Created **dimension** and **fact** tables.  
- Optimized for analytics & BI dashboards.  
- Ensured keys and relationships are business-ready.  

---

## 🔄 SCD Implementations

### SCD Type 1 – Overwrite
- Used `MERGE INTO` to update product/customer details.  
- Only **latest truth** retained, no history tracked.  

### SCD Type 2 – Track History
- Added metadata columns:  
  - `start_date`  
  - `end_date`  
  - `is_current`  
- Inserted a **new row for each change** while closing old rows.  
- Full history preserved for analytics (e.g., *“what was category in 2023?”*).  

---

## 🎯 Achievements
- Built an **end-to-end pipeline** (raw → cleaned → analytics-ready).  
- Demonstrated **real-world change tracking** with SCD 1 & 2.  
- Hands-on practice with **Spark SQL, Databricks, and Data Warehousing**.  
