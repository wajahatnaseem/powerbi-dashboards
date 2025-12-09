# 📊 Executive Sales Performance Dashboard (Power BI)

![Dashboard Preview](./assets/dashboard-preview.png)

This project presents an **interactive Executive Sales Performance Dashboard** built using **Power BI**.  
It is designed to help business users analyze **Revenue, Cost (COGS), Profit, and Profit Margin** across multiple dimensions such as **Product Type, Retailer Type, Order Method, Time, and Geography**.

This dashboard is specifically created for:
- ✅ **Data Analyst / Business Intelligence Interviews**
- ✅ **Portfolio Presentation**
- ✅ **Executive Business Reporting Use Cases**

---

## 🎯 Business Objectives

This dashboard helps answer key business questions such as:

- Which **product types generate the highest revenue and profit**?
- How does business performance **trend month-wise and year-wise**?
- Which **order method** contributes the most to profit?
- Which **countries and cities** drive the most value?
- How efficiently is the business converting **cost into profit**?

---

## 🚀 Key Features

- ✅ **Dynamic KPI Switching** (COGS / Profit / Revenue)
- ✅ **Year-Based Comparison** (2016 & 2017)
- ✅ **Executive KPI Cards**
  - Total Revenue  
  - Total Cost (COGS)  
  - Total Profit  
  - Profit Margin %
- ✅ **Monthly Trend Analysis**
- ✅ **Product Type Performance Breakdown**
- ✅ **Top Retailer Type Comparison**
- ✅ **Geographical Performance by Country**
- ✅ **Dynamic Tooltips for Deep Insights**
- ✅ **Modern, Clean Executive Layout**

---

## ▶️ How to Use This Dashboard

1. Use the **Year slicer** to switch between **2016 and 2017**.
2. Use the **KPI selector** to dynamically switch between:
   - COGS
   - Profit
   - Revenue
3. Select different **product categories** from the top:
   - Camping Equipment  
   - Mountaineering Equipment  
   - Outdoor Protection  
4. Hover over charts to view **dynamic tooltips with deeper breakdowns**.

---

## 🧠 Data Model Overview

This dashboard uses a **Star Schema Data Model**:

- **Fact Table:** `Sales`
- **Dimension Tables:**
  - `Date`
  - `Product`
  - `City`
- **Disconnected Table:**
  - `KPI` (used for dynamic KPI switching through DAX)

All calculations are implemented as **DAX measures** to preserve **filter context and performance**.

---

## 🧮 Key DAX Measures Used

```DAX
Total Revenue = SUM(Sales[Revenue])
Total COGS = SUM(Sales[COGS])
Total Profit = SUM(Sales[Profit])

Margin % = DIVIDE([Total Profit], [Total Revenue])

Selected KPI Value :=
SWITCH(
    SELECTEDVALUE(KPI[KPI]),
    "Cogs", [Total COGS],
    "Profit", [Total Profit],
    "Revenue", [Total Revenue]
)
