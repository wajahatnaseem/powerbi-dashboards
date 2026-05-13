# ✈️ Airline Operations Performance Dashboard (Power BI)

![Dashboard Preview](./Airline-Operations-Performance-Dashboard.png)

[![Power BI](https://img.shields.io/badge/View-Live%20Dashboard-yellow?logo=powerbi)](https://app.powerbi.com/view?r=eyJrIjoiMmU4YWI1MWYtMTk0ZS00NzljLWIyYzctMDM4YjQxMjA5ZTE1IiwidCI6IjFkZjNkMzdmLTkzZGMtNDI5Ny1hYzcyLTRhNWYzZWVkZmNmMiJ9)

## 🌐 Live Dashboard

🔗 Click the dashboard preview image above or the badge to open the interactive Power BI report.

---

## 📌 Project Overview

This project presents an **interactive Airline Operations Performance Dashboard** built using **Power BI**.  
The dashboard focuses on analyzing:

- Flight operations
- Flight delays
- Flight cancellations
- Airline operational efficiency
- Airport traffic performance
- Delay reason distribution

The goal of this dashboard is to help identify:
- Operational bottlenecks
- Delay patterns
- Airline performance trends
- Airport traffic concentration
- Flight status distribution

This project is designed for:

- ✅ Data Analyst / Business Intelligence Interviews
- ✅ Operational Analytics Demonstrations
- ✅ Portfolio & Dashboard Showcasing
- ✅ Aviation Performance Reporting

---

# 🎯 Business Objectives

This dashboard helps answer important business and operational questions such as:

- Which airlines maintain the best on-time performance?
- What are the major causes of delays and cancellations?
- Which airports handle the highest flight traffic?
- How do operational metrics vary across airlines?
- What percentage of flights are:
  - On-Time
  - Delayed
  - Cancelled

---

# 🚀 Key Features

- ✅ Interactive KPI Dashboard
- ✅ Airline Performance Analysis
- ✅ Airport Traffic Analysis
- ✅ Flight Delay Monitoring
- ✅ Cancellation Analysis
- ✅ Delay Reason Distribution
- ✅ Operational KPI Tracking
- ✅ Interactive Visualizations
- ✅ Minimal & Executive Dashboard Design

---

# 📊 KPIs Tracked

The dashboard tracks the following key operational metrics:

- Total Flights
- Delayed Flights
- Cancelled Flights
- On-Time Flights
- Delay Percentage
- Cancellation Percentage
- On-Time Percentage
- Airline Performance Metrics
- Airport Traffic Volume

---

# ▶️ Dashboard Walkthrough

## 🔹 KPI Cards

The top section displays high-level operational KPIs such as:

- Total Flights
- Delayed Flights
- Cancelled Flights
- Trend Indicators

These KPIs provide quick executive-level operational monitoring.

---

## 🔹 Airport Traffic Analysis

Analyzes airports based on:

- Total Flights
- Traffic Volume
- Delay Concentration
- Operational Bottlenecks

This helps identify high-traffic and high-delay airports.

---

## 🔹 Airline Performance Analysis

Compares airlines using:

- On-Time Performance
- Delay Percentage
- Operational Consistency
- Flight Efficiency

This helps evaluate operational performance across carriers.

---

## 🔹 Delay Reason Analysis

Delays and cancellations are categorized into:

- Weather
- Airline/Carrier
- National Air System
- Security

This enables root-cause analysis of operational disruptions.

---

## 🔹 Flight Status Distribution

Displays operational distribution of flights into:

- On-Time
- Delayed
- Cancelled

for quick operational performance evaluation.

---

# 🧠 Data Model Overview

The dashboard follows a **Star Schema-inspired Data Model** for optimized performance and analytical flexibility.

---

## 📌 Fact Table

### `flights`

The central fact table contains operational flight-level metrics and transactional flight data.

### Key Fields:
- `AIRLINE`
- `ORIGIN_AIRPORT`
- `CANCELLATION_REASON`
- `DEPARTURE_DELAY`
- `YEAR`
- `MONTH`
- `DAY`
- `DAY_OF_WEEK`
- `Status`

### Calculated Measures:
- `% Cancelled`
- `% Delayed`
- `% On-Time Flights`
- `Cancelled Flights`
- `Delayed Flights`
- `On-Time Flights`
- `Total Flights`

---

## 📌 Dimension Tables

### `airlines`
Contains airline reference information.

#### Fields:
- `AIRLINE`
- `IATA_CODE`

---

### `airports`
Contains airport and geographical information.

#### Fields:
- `AIRPORT`
- `CITY`
- `STATE`
- `COUNTRY`
- `IATA_CODE`
- `LATITUDE`
- `LONGITUDE`

---

### `cancellation_codes`
Contains cancellation reason mappings.

#### Fields:
- `CANCELLATION_REASON`
- `CANCELLATION_DESCRIPTION`

---

### `Dim_Days`
Used for day-level operational analysis.

#### Fields:
- `Day Name`
- `Day_Name`
- `Day_of_Week`

---

### `DimDayNew`
Used for sorting and display optimization.

#### Fields:
- `DayName`
- `DayNumber`

---

# 🔗 Relationships & Model Design

The model uses one-to-many relationships between:

- Airlines → Flights
- Airports → Flights
- Cancellation Codes → Flights
- Day Dimensions → Flights

This structure enables:

- Faster filtering
- Better DAX performance
- Scalable reporting
- Clean analytical relationships
- Efficient operational slicing

---

# 🧮 Key DAX Measures Used

```DAX
Total Flights =
COUNTROWS(flights)

Delayed Flights =
CALCULATE(
    [Total Flights],
    flights[Status] = "Delayed"
)

Cancelled Flights =
CALCULATE(
    [Total Flights],
    flights[CANCELLED] = 1
)

On-Time Flights =
CALCULATE(
    [Total Flights],
    flights[Status] = "On-Time"
)

% Delayed =
DIVIDE(
    [Delayed Flights],
    [Total Flights]
)

% Cancelled =
DIVIDE(
    [Cancelled Flights],
    [Total Flights]
)

% On-Time Flights =
DIVIDE(
    [On-Time Flights],
    [Total Flights]
)
