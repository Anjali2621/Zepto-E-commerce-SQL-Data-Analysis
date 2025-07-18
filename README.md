 🛒 Zepto E-commerce SQL Data Analysis Project
 
 This is a complete, real-world **data analyst portfolio project** based on a dynamic inventory dataset scraped from **Zepto** — one of India’s fastest-growing quick-commerce startups. This project walks you through the **real-life workflow of a data analyst**, starting from raw CSV files to business-critical SQL insights.


📌 Project Goals

This project simulates how real data analysts in fast-paced retail or e-commerce teams work behind the scenes. Using SQL, we:

- 📦 Set up and model an inventory database from raw product listings  
- 🔍 Conduct **Exploratory Data Analysis (EDA)** on product categories, stock levels, and pricing mismatches  
- 🧹 Perform **Data Cleaning**, including unit conversions and filtering invalid records  
- 📊 Write **insightful, business-driven SQL queries** that focus on discounts, pricing strategies, availability, and revenue metrics


 📁 Dataset Overview

The dataset is publicly available on **Kaggle**, originally scraped from Zepto's online product catalog. It mirrors what you'd typically see in a real e-commerce inventory system.

Each record represents a unique SKU (Stock Keeping Unit) — meaning a product can appear multiple times in different sizes, weights, or discounts, just like in real retail systems.

# 🔢 Key Columns:

- `sku_id`: Unique ID for each product entry (synthetic primary key)
- `name`: Product name (e.g., "Tata Salt", "Amul Milk")
- `category`: Category like Fruits, Snacks, Dairy, etc.
- `mrp`: Maximum Retail Price (converted from paise to ₹)
- `discountPercent`: Discount applied to MRP
- `discountedSellingPrice`: Final price after discount (in ₹)
- `availableQuantity`: Stock quantity available
- `weightInGms`: Product weight in grams
- `outOfStock`: Boolean value (true/false)
- `quantity`: Units per package (or grams for loose items)


🔧 Workflow Breakdown

# 1️⃣ Table Creation
Created a SQL table with appropriate data types using:

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

🛠️ Data Import
Used pgAdmin’s import tool to load the dataset.


📦 Data Exploration
-Total number of products in the catalog
-Sampling rows to understand structure
-Null value detection across all fields
-Distribution of product categories
-Stock availability analysis (in-stock vs. out-of-stock)
-Duplicate detection for same products with varying sizes/prices.


🧹 Data Cleaning
-Removed products where MRP or discounted price was zero
-Converted prices from paise to rupees
-Handled type mismatches or invalid rows
-Ensured consistency in numeric fields (weights, prices)


🧠 Business Analysis Queries
🔟 Top 10 best-value products (highest discount %)

🚫 High-MRP items currently out of stock

📈 Estimated potential revenue by category

💰 Expensive products (MRP > ₹500) with negligible discounts

🏷️ Top 5 categories offering highest average discounts

⚖️ Price-per-gram comparisons to identify value picks

🧱 Inventory categorization by weight: Light / Medium / Bulk

🏋️ Total weight in stock per category
