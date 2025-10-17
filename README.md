## 🛒 Zepto E-commerce SQL Data Analyst Portfolio Project

This is a complete, real-world data analyst portfolio project based on an e-commerce inventory dataset scraped from Zepto — one of India’s fastest-growing quick-commerce startups. This project simulates real analyst workflows, from raw data exploration to business-focused data analysis.

## 📌 Project Overview

The goal of this project is to mirror how data analysts in e-commerce and retail industries use SQL to:

✅ Set up and understand messy, real-world inventory data

✅ Perform Exploratory Data Analysis (EDA) to examine product categories, availability, and pricing inconsistencies

✅ Clean the dataset by fixing nulls, removing invalid entries, and converting pricing from paise to rupees

✅ Run business-driven SQL queries to uncover insights about pricing, stock, revenue, and discount patterns

## 📁 Dataset Overview

The dataset was sourced from [Kaggle](https://www.kaggle.com/datasets/palvinder2006/zepto-inventory-dataset/data?select=zepto_v2.csv) and originally scraped from Zepto’s product listings.

It reflects the structure of a real inventory database — where duplicate product names exist due to different packaging sizes, weights, and discounts across categories.

Each row represents a unique SKU (Stock Keeping Unit) for a product. Duplicate product names exist because the same product may appear multiple times in different package sizes, weights, discounts, or categories to improve visibility – exactly how real catalog data looks.

## 🧾 Columns:

sku_id – Unique identifier for each product

name – Product name as listed on Zepto

category – Category such as Fruits, Snacks, Beverages, etc.

mrp – Maximum Retail Price (originally in paise, later converted to ₹)

discountPercent – Discount percentage on MRP

discountedSellingPrice – Final selling price after discount (in ₹)

availableQuantity – Inventory units available

weightInGms – Product weight in grams

outOfStock – Boolean showing stock status

quantity – Number of units per package

## 🔧 Project Workflow

Here’s a step-by-step breakdown of what we do in this project:

**1️⃣ Database & Table Creation**

Created a table named zepto with suitable data types for each field:

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

**2️⃣ Data Import**

Imported the CSV file into PostgreSQL using pgAdmin.

**3️⃣ Data Exploration**

Counted total rows and viewed sample data

Checked for null values in key columns

Listed all distinct product categories

Compared in-stock vs out-of-stock products

Detected duplicate product names representing multiple SKUs

**4️⃣  Data Cleaning**

Removed rows where mrp or discountedSellingPrice = 0

Converted paise → rupees for mrp and discountedSellingPrice

Ensured all remaining fields were consistent and valid

**5️⃣ Business Insights**

Top 10 best-value products based on discount %

High-MRP products that are out of stock

Estimated revenue by product category

Premium products (MRP > ₹500) with low discounts (<10%)

Top 5 categories with the highest average discount

Calculated price per gram for best value-for-money products

Classified items by weight range (Low / Medium / Bulk)

Total inventory weight per category

## ✨ Author

 **Fareehah Chorghay**
📍 [LinkedIn](https://www.linkedin.com/in/fareehah-chorghay/)
📧 [fareehah.c@gmail.com](mailto:fareehah)
