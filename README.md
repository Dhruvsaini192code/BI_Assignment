# 📊 Fabric Sales Analytics — End-to-End Project

## 🚀 Project Overview

This project demonstrates a complete **end-to-end analytics solution** built using **Microsoft Fabric and Power BI**.

The goal is to transform raw Excel-based sales data into a **scalable, production-ready analytics system** with:

* Data ingestion
* Transformation (Bronze → Silver → Gold)
* Star schema modeling
* Advanced DAX calculations
* Interactive multi-page dashboard

---

## 🏗️ Architecture Overview

The project follows a modern **Fabric Lakehouse architecture**:

```
Excel Data → Dataflow Gen2 → Lakehouse (Delta Tables)
           → Semantic Model (DirectLake)
           → Power BI Report (Dashboard)
```

### 🔹 Layers Explained

| Layer     | Tool                    | Description                   |
| --------- | ----------------------- | ----------------------------- |
| Ingestion | Dataflow Gen2           | Load and transform Excel data |
| Storage   | Lakehouse (OneLake)     | Central Delta storage         |
| Modeling  | Power BI Semantic Model | Relationships + DAX           |
| Reporting | Power BI                | Interactive dashboards        |

---

## 📂 Dataset

* Source: Sales Data for Fabric (Excel)
* Includes:

  * Sales Transactions
  * Item Data (Split across multiple tables)
  * Customer Data
  * Geography Data
  * Category / Brand / SubCategory

---

## ⚙️ Data Ingestion Approach

### ✅ Chosen Path: **Dataflow Gen2 (Path A)**

**Steps followed:**

1. Uploaded Excel file to Lakehouse
2. Created Dataflow Gen2
3. Loaded all sheets
4. Applied transformations using Power Query
5. Saved outputs as Delta tables

---

## 🔄 Data Transformation

### 🥉 Bronze Layer

* Raw data loaded as-is

### 🥈 Silver Layer (Cleaned & Modeled)

#### Fact Table

* `silver_Sales`

  * One row per order line
  * Includes calculated columns

#### Dimension Tables

* `silver_Item` (Merged dataset)
* `silver_Customer` (Deduplicated + AgeGroup)
* `silver_Geography` (Cleaned location data)
* `dim_Date` (Custom date table)

---

## ⭐ Star Schema

```
          dim_Date
              |
              |
silver_Customer — silver_Sales — silver_Item
              |
       silver_Geography
```

---

## 📐 Calculations

### 🧮 Calculated Columns

* Gross Amount
* Discount Amount
* COGS
* Net Amount
* Margin

### 📊 Measures

#### Base Metrics

* Gross
* Net
* Discount
* Margin
* Margin %

#### Time Intelligence

* MTD / QTD / YTD
* YoY %
* Rolling 3 Months

#### Advanced Analytics

* Cohort Analysis
* Customer Retention
* ABC Classification
* RFM Segmentation

---

## 📈 Report Pages

### 1️⃣ Executive Overview

* KPI Cards (Net Sales, MoM %, Margin %)
* Sales Trend (YoY)
* Map (Sales by State)

### 2️⃣ Time Insights

* Time Intelligence comparison
* Rolling trends
* Delivery delay analysis

### 3️⃣ Customer & Cohort

* Cohort Matrix
* Retention Analysis
* Age Group insights

### 4️⃣ ABC Classification

* Product segmentation (A / B / C)
* Revenue contribution

### 5️⃣ Quadrant Analysis

* Discount % vs Margin %
* Performance clustering

### 6️⃣ Advanced Analysis

* Decomposition Tree
* Dynamic Measures
* Unsold Products analysis

### 7️⃣ Top / Bottom Analysis

* Top & Bottom Products
* Margin & Discount insights

---

## 🧠 Key Insights

* Identified top-performing products contributing majority revenue
* Highlighted customer retention patterns
* Detected high discount but low margin segments
* Revealed operational inefficiencies (delivery delays)

---

## ✅ Validation & Quality Checks

* ✔ Star schema relationships validated
* ✔ No duplicate keys in dimensions
* ✔ DAX reconciliation checks passed
* ✔ EXCEPT validation performed for Item table
* ✔ Date table covers full range

---

## ⚡ Technologies Used

* Microsoft Fabric
* Dataflow Gen2
* Lakehouse (OneLake)
* Power BI (Semantic Model + Reports)
* DAX
* Power Query

---

## 📊 Key Features

* DirectLake Mode (No refresh required)
* Scalable Lakehouse architecture
* Advanced DAX analytics
* Interactive dashboards
* Clean star schema modeling

---

## 📌 How to Use

1. Open the repository
2. Review Dataflow transformations
3. Connect to Semantic Model
4. Open Power BI Report
5. Explore dashboards using slicers

---

## 🎯 Learning Outcomes

* Built a full Fabric data pipeline
* Learned Lakehouse architecture
* Designed star schema
* Applied advanced DAX techniques
* Created business-ready dashboards

---

## 📎 Repository

🔗 GitHub:
https://github.com/Dhruvsaini192code/BI_Assignment

---

## 👤 Author

**Dhruv Saini**
Aspiring Data Analyst | Power BI & Microsoft Fabric Enthusiast

---

## 🌟 Final Note

This project simulates a **real-world enterprise analytics solution**, combining **data engineering + data modeling + business intelligence** into one unified workflow using Microsoft Fabric.

---
