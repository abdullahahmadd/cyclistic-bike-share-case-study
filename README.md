# 🚴‍♂️ Cyclistic Bike-Share Case Study — Google Data Analytics Capstone  
### *Excel • SQL • R | End-to-End Data Analytics Project*

---

## 📌 Overview

This project analyzes data from the **Cyclistic Divvy Q1 2020 bike-share dataset**, originally containing over **300,000 rows**.  
To ensure smooth performance across tools, the dataset was reduced to **8,036 rows** while preserving distribution and patterns.

The goal of the project is to understand **how casual riders and annual members use Cyclistic bikes differently**, and develop **data-driven marketing recommendations** to increase annual membership conversions.

The analysis follows the **Google Data Analytics process**:  
**Ask → Prepare → Process → Analyze → Share → Act**

Work was performed in **Excel**, **MySQL**, and **R (tidyverse, lubridate, ggplot2)**.

---

## 📂 Project Files

| File Name | Description |
|-----------|-------------|
| `cyclistic_analysis.xlsx` | Excel cleaning, pivot tables, dashboards, KPI metrics |
| `cyclistic_analysis.sql` | SQL cleaning + analysis queries |
| `cyclistic_analysis.R` | R data cleaning, analysis, ggplot visualizations |
| `cyclistic_workspace.RData` | Saved R environment |
| `README.md` | Documentation of entire project |

---

## 🧵 Dataset Story

### **Original Attributes (Raw Dataset)**
- `ride_id`  
- `rideable_type`  
- `started_at`, `ended_at`  
- `start_station_name`, `start_station_id`  
- `end_station_name`, `end_station_id`  
- `start_lat`, `start_lng`, `end_lat`, `end_lng`  
- `member_casual`

### **New Attributes Created (Process Phase)**

**Excel:**
- `ride_length`
- `day_of_week`
- `start_hour`
- `start_month`

**SQL:**
- `started_at_dt`, `ended_at_dt`
- `ride_length_secs`, `ride_length_mins`

**R:**
- `weekday` (ordered)
- `started_hour_new`
- `started_month_new`
- `started_date`
- `is_weekend`

These engineered features allowed deeper behavioral analysis.

---

## 🧠 ASK — Define the Business Task

**Key Question:**  
> How do annual members and casual riders use Cyclistic bikes differently?

Cyclistic aims to **convert casual riders into annual members** using targeted marketing campaigns.

---

## 🗄 PREPARE — Data Source & Credibility

- Dataset: Divvy Q1 2020 public data  
- License: Motivate International Inc.  
- No PII included  
- Data stored in Excel, MySQL, and R  
- Follows ROCCC: Reliable, Original, Comprehensive, Current, Cited  

---

## 🧹 PROCESS — Cleaning & Feature Engineering

### **Excel**
- Converted timestamps  
- Calculated ride length  
- Added weekday, hour, and month columns  
- Removed invalid or zero-duration rides  

### **SQL (MySQL 8.0 Workbench)**
- Imported CSV → table `trips`  
- Casted datetime fields  
- Calculated ride duration in minutes/seconds  
- Generated hourly and weekday metadata  
<img width="790" height="459" alt="total_rows_sql" src="https://github.com/user-attachments/assets/83d6262b-9a39-4d9e-9a1f-d0138a4ea5fd" />
<img width="790" height="459" alt="missing_values_sql" src="https://github.com/user-attachments/assets/fef1ee33-c4ef-422c-b1c1-9e0dc4916682" />
<img width="790" height="459" alt="10_rows_sql" src="https://github.com/user-attachments/assets/5490b4c1-8a09-447e-ace3-c99695d73854" />
<img width="793" height="466" alt="avg_ride_minutes_sql" src="https://github.com/user-attachments/assets/844d86bb-baec-47af-9078-19261775b2ed" />
<img width="789" height="471" alt="max_ride_minutes" src="https://github.com/user-attachments/assets/660d5ee0-cfa4-44d1-815a-8cc14d04f889" />
<img width="788" height="473" alt="ride_length_and_secs_sql" src="https://github.com/user-attachments/assets/929001e3-d9c2-42d0-ab2f-a1d7fff2ebd5" />
<img width="788" height="473" alt="hightest_day_of_week_sql" src="https://github.com/user-attachments/assets/bb1aa7ad-a1bb-40f7-b8fc-825c3c422a02" />
<img width="795" height="471" alt="member_casual_avg_ride_mints_Sql" src="https://github.com/user-attachments/assets/e2b58a4c-c58c-4ca1-bfa5-f23ab21c2d5c" />
<img width="794" height="476" alt="member_casual_total_rides_sql" src="https://github.com/user-attachments/assets/336b718f-15d2-4fb2-aef4-fdf316e3743b" />
<img width="790" height="472" alt="hightest_rides_by_hour_sql" src="https://github.com/user-attachments/assets/c88ddf27-b8da-4ad5-aca4-6840935be152" />
<img width="795" height="471" alt="hightest_rides_by_month_sql" src="https://github.com/user-attachments/assets/bfc7d57c-c17d-4dd9-9d25-55853ea610f0" />

### **R (tidyverse + lubridate)**
- Cleaned names  
- Parsed timestamps into POSIX  
- Derived new fields (`weekday`, `is_weekend`, etc.)  
- Removed invalid entries  
- Performed grouped calculations  
- Built visualizations using ggplot2  

---

## 📊 ANALYZE — Key Findings

### **Ride Duration**
- Casuals: **Longer rides** (~388 mins avg)  
- Members: **Shorter rides** (~279 mins avg)

### **Usage Volume**
- Members take **90%+ of all trips** (7,621 vs 414)

### **Day Patterns**
- Casual peaks: **Tuesday, Wednesday, Thursday, weekends**  
- Members: stable **weekday** usage (commuters)

### **Hourly Patterns**
- Members: peaks at **7–9 AM** + **4–6 PM**  
- Casuals: **midday + afternoon** patterns  

### **Geographic Hotspots**
Top casual stations are located at:
- Michigan Ave & Washington St  
- Millennium Park  
- Lake Shore Dr & Monroe St  

These are **high-tourism or leisure locations**.

---

## 📈 SHARE — Visualizations

Visualizations created in **Excel** and **R (ggplot2)**.

📌 **Excel Visualizations Section**  
<img width="1364" height="541" alt="excel_dashboard" src="https://github.com/user-attachments/assets/cd65b67f-3aa0-4d62-aa05-791e8d2d667d" />

📌 **R Visualization (ggplot) Section**  
<img width="651" height="391" alt="ride_length_summary_R" src="https://github.com/user-attachments/assets/904c5af8-1f0d-4301-98b1-e446a7ec0385" />
<img width="651" height="391" alt="avg_ride_length_R" src="https://github.com/user-attachments/assets/c7f34aac-a2b9-4cdc-95e5-4be0a3bf2f69" />
<img width="651" height="391" alt="avg_ride_length_by_week_of_day" src="https://github.com/user-attachments/assets/012c3695-9f3d-4f96-892f-dce15a7e09c4" />
<img width="651" height="391" alt="number_of_rides_by_day_R" src="https://github.com/user-attachments/assets/aaa510a4-812b-4db8-802a-8d3c4d53fe80" />
<img width="651" height="391" alt="hourly_usage_pattern_by_user_type_R" src="https://github.com/user-attachments/assets/7f11bf0e-c014-4355-b8a9-947b18a100ed" />
<img width="651" height="391" alt="top_start_stations_by_user_type_R" src="https://github.com/user-attachments/assets/34d1e63f-f090-45ae-913b-1af2b82b3a79" />

---

## 🧭 ACT — Final Recommendations

### **1️⃣ Target casual riders at leisure-heavy stations**  
Place QR codes, in-app ads, and promotions at:
- Millennium Park  
- Lakefront  
- Michigan Ave hubs  

### **2️⃣ Introduce a weekend or tourist-focused membership**  
Examples:
- **Weekend Unlimited Pass**  
- **Visitor → Monthly Upgrade Discount**  

### **3️⃣ Use digital media to highlight value for casual riders**  
Emphasize:
- Cost savings  
- Convenience  
- Unlimited rides  
- Rewards/points  

These align with casual riders’ behaviors.

---


