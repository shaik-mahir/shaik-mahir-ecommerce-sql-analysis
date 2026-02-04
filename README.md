# shaik-mahir-ecommerce-sql-analysis

# 🛒 Zepto E-Commerce Inventory Analysis using SQL
**Author:** Shaik Mahir  

SQL data analysis project analyzing Zepto-style e-commerce product inventory data to generate business insights using SQL queries and reporting techniques.

---

## 📌 Project Overview
This project simulates how real-world data analysts work in the e-commerce and retail industry by using SQL to manage, clean, and analyze inventory data.

The project focuses on building a realistic e-commerce inventory database and generating business insights through structured SQL queries.

### ✅ Key Objectives
- Create a real-world messy inventory database
- Perform Exploratory Data Analysis (EDA)
- Clean and preprocess inconsistent data
- Generate business-driven insights using SQL
- Analyze pricing, discounts, inventory, and product value

---

## 📁 Dataset Overview
The dataset was sourced from Kaggle and originally scraped from Zepto’s official product listings.

Each row represents a unique **SKU (Stock Keeping Unit)**.  
Duplicate product names exist because products appear in multiple package sizes, weights, or discount variations — reflecting real-world catalog structures.

---

## 🧾 Dataset Columns

| Column | Description |
|--------|-------------|
| sku_id | Unique identifier for each product |
| name | Product name |
| category | Product category |
| mrp | Maximum Retail Price (₹) |
| discountPercent | Discount percentage |
| discountedSellingPrice | Final selling price (₹) |
| availableQuantity | Inventory units available |
| weightInGms | Product weight in grams |
| outOfStock | Stock availability flag |
| quantity | Units per package |

---

## 🛠️ Tech Stack
- SQL (PostgreSQL)
- pgAdmin
- CSV Dataset
- Data Cleaning & Analysis
- Business Intelligence Queries

---

## 🔧 Project Workflow

### 1️⃣ Database & Table Creation
```sql
CREATE TABLE zepto (
  sku_id SERIAL PRIMARY KEY,
  category VARCHAR(120),
  name VARCHAR(150) NOT NULL,
  mrp NUMERIC(8,2),
  discountPercent NUMERIC(5,2),
  availableQuantity INTEGER,
  discountedSellingPrice NUMERIC(8,2),
  weightInGms INTEGER,
  outOfStock BOOLEAN,
  quantity INTEGER
);
```

---

## 📥 Data Import

The dataset was imported into PostgreSQL using pgAdmin CSV import and the COPY command.

### Import Method
- Imported CSV file into PostgreSQL table using pgAdmin
- Ensured proper column mapping during import
- Verified data after loading into the database

### SQL Import Command
\copy zepto(category,name,mrp,discountPercent,availableQuantity,
discountedSellingPrice,weightInGms,outOfStock,quantity)
FROM 'data/zepto_v2.csv'
WITH (FORMAT csv, HEADER true, DELIMITER ',', QUOTE '"', ENCODING 'UTF8');

### Data Preparation
- Fixed UTF-8 encoding issues by saving CSV file in UTF-8 format
- Checked for missing values and data inconsistencies after import

---

### 3️⃣ 🔍 Exploratory Data Analysis
- Counted total records
- Viewed sample dataset
- Checked null values
- Identified distinct product categories
- Compared stock vs out-of-stock items
- Found duplicate products across different SKUs

---

### 4️⃣ 🧹 Data Cleaning
- Removed invalid records (zero price entries)
- Converted prices from paise to rupees
- Standardized pricing for analysis

---

### 5️⃣ 📊 Business Insights
- Top 10 best-value products based on discounts
- High-MRP products currently out of stock
- Estimated revenue per category
- Expensive products with minimal discount
- Top 5 categories with highest average discounts
- Price-per-gram analysis for value products
- Weight-based product segmentation
- Total inventory weight per category

---

## 📈 Key Skills Demonstrated
- SQL Query Writing
- Data Cleaning & Transformation
- Exploratory Data Analysis
- Business Analytics
- Inventory Analysis
- Real-world Dataset Handling

---

## 🎯 Project Purpose
This project demonstrates practical SQL skills used by data analysts in real e-commerce environments to extract insights, optimize pricing strategies, and manage inventory effectively.

---

## ⭐ Author
**Shaik Mahir**
```
GitHub: https://github.com/shaik-mahir-ecommerce-sql-analysis
```
