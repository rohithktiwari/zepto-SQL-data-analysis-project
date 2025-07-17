
# 🛒 Zepto E-commerce SQL Data Analysis Project

This project demonstrates real-world SQL data analysis skills using an e-commerce inventory dataset from Zepto — a popular Indian quick-commerce platform. The goal is to simulate how data analysts clean, explore, and extract business insights from raw product data using SQL.

---

## 📌 Project Highlights

✅ End-to-end SQL project: from raw CSV to insightful business queries
✅ Real-world dataset with inconsistencies, nulls, duplicates
✅ Focused on key retail metrics: stock, discounting, pricing, inventory, etc.
✅ Perfect for data analyst resumes, LinkedIn, or interview prep

---

## 📁 Dataset Overview

* **Source**: Zepto product listings (scraped and made available on Kaggle)
* **Format**: CSV
* **Size**: \~6,000+ rows, representing unique product SKUs

### Columns

| Column                   | Description                               |
| ------------------------ | ----------------------------------------- |
| `sku_id`                 | Unique identifier (synthetic primary key) |
| `name`                   | Product name                              |
| `category`               | Product category                          |
| `mrp`                    | Maximum Retail Price (in ₹)               |
| `discountPercent`        | Discount on MRP                           |
| `discountedSellingPrice` | Final selling price (in ₹)                |
| `availableQuantity`      | Units in stock                            |
| `weightInGms`            | Weight in grams                           |
| `outOfStock`             | Boolean: In stock or not                  |
| `quantity`               | Number of units in package                |

---

## 🛠️ Tools & Stack

* **SQL**: PostgreSQL
* **IDE**: pgAdmin / VS Code
* **Version Control**: Git + GitHub

---

## 🔧 Project Workflow

### 1. Database & Table Setup

```sql
CREATE TABLE zepto_table (
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

### 2. Data Import

```bash
\copy zepto_table(category,name,mrp,discountPercent,availableQuantity,
  discountedSellingPrice,weightInGms,outOfStock,quantity)
FROM 'data/zepto_v2.csv' WITH (FORMAT csv, HEADER true, DELIMITER ',', QUOTE '"', ENCODING 'UTF8');
```

### 3. Data Exploration

* Total records in dataset
* Null values check
* Distinct categories
* Stock status distribution
* Duplicate product names

### 4. Data Cleaning

* Removed zero-value products (`MRP = 0 OR discountedSellingPrice = 0`)
* Converted paise to rupees for price columns
* Dropped unnecessary rows

### 5. 📊 Business Insights (Sample)

* 🔟 Top 10 best discount products
* 📦 High MRP items that are out of stock
* 📈 Estimated revenue by category
* 🧂 Category-wise average discount %
* 💰 Products offering best price per gram
* ⚖️ Weight-based classification (Low/Medium/Bulk)
* 🏋️‍♂️ Total inventory weight per category

---

## 📸 Screenshots

Included in `/images/`:

* Full Table Preview
* Null Value Check
* In-Stock vs Out-of-Stock Distribution
* Query Outputs (each named clearly for reference)

---

## 🧾 File Structure

```bash
zepto_sql_data_analysis_project/
│
├── zepto_queries.sql           # All SQL queries (exploration, cleaning, analysis)
├── zepto_v2.csv                # Dataset
├── README.md                   # Project documentation
└── images/                     # Screenshots (query output, charts, etc.)
```

--



## 📬 Contact

- 📧 rohithktiwari@gmail.com  
- 🔗 [LinkedIn](https://www.linkedin.com/in/rohithktiwari/)  
- 🧑‍💻 GitHub: [rohithktiwari]

---

## 📜 License

This project is open source under the MIT License — feel free to fork, modify, and share!

---

