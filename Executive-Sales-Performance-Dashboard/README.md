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

Additional metrics include:

YoY Growth %

Rolling 3-Month Average

Dynamic Ranking

Contribution %

📌 Key Business Insights (Sample)

Outdoor Protection shows strong profit contribution compared to other categories.

Web-based orders generate the highest revenue share.

Seasonal revenue peaks are visible during mid-year months.

Some regions show high revenue but lower margin, indicating cost optimization opportunities.

🧠 Skills Demonstrated

Power BI Dashboard Development

Star Schema Data Modeling

Advanced DAX Measures

Dynamic KPI Switching using Disconnected Tables

Time Intelligence (YoY, Monthly Trends)

Interactive Tooltips

Business-Oriented Data Storytelling

Executive Dashboard UI Design

🧰 Tools & Technologies

Power BI Desktop

DAX (Data Analysis Expressions)

Microsoft Excel (Data Preparation)

Star Schema Modeling

Azure Maps / Modern Map Visuals

⬇️ Download Instructions

Click on the .pbix file in this repository.

Click View Raw to download.

Open the file using Power BI Desktop.

⚠️ Disclaimer

The dataset used in this project is for demonstration and learning purposes only.

This dashboard does not represent real company data.

Some visuals may require map permissions to be enabled in Power BI.

👤 Author

Wajahat Naseem
Aspiring Data Analyst | Power BI Developer
🔗 GitHub: https://github.com/wajahatnaseem

⭐ Support

If you find this project useful:

⭐ Star this repository

🍴 Fork it to build your own version

💬 Share your feedback or suggestions

Thank you for visiting!


---

