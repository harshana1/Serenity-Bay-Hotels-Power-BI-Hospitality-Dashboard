# 🏨 Serenity Bay Hotels – Power BI Hospitality Dashboard  

![Power BI](https://img.shields.io/badge/PowerBI-Dashboard-F2C811?logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Analytics-blue?logo=microsoft)
![Kaggle](https://img.shields.io/badge/Kaggle-Dataset-20BEFF?logo=kaggle)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

---

🚀 **Power BI Project | Hospitality Analytics | End-to-End Dashboard**

This project explores real hotel booking data to uncover insights on **revenue**, **occupancy**, and **guest behavior** in the hospitality industry.  
It uses the **Hotel Bookings dataset from Kaggle** to demonstrate how **business intelligence** can support strategic hotel management.

---

## 🎯 Project Objective  

To design a Power BI dashboard that provides decision-makers with data-driven insights into:
- Revenue & occupancy trends  
- Cancellation behaviors  
- Guest types & market segments  
- Country-based revenue performance  

---

## 🧩 Key Features  

✅ **ETL with Power Query** – Cleaned and transformed Kaggle dataset  
✅ **Data Modeling** – Built a star schema with fact and dimension tables  
✅ **Custom DAX Measures** – Created advanced KPIs for business decisions  
✅ **Dynamic Slicers** – Hotel Type, Year, Month, Market Segment, Country  
✅ **Professional Navigation Buttons** – Multi-page interactive design  
✅ **Three Insightful Dashboard Pages**  

---

## 📁 Dashboard Pages  

### 📄 1️⃣ Executive Overview  
- KPIs: Total Revenue, ADR, RevPAR, Occupancy %, Cancellation %  
- Line Chart: Revenue & Occupancy by Month-Year  
- Pie Chart: Bookings vs. Cancellations  

### 📄 2️⃣ Revenue & Booking Analysis  
- Column Chart: Revenue by Market Segment  
- Bar Chart: Revenue by Reserved Room Type  
- Table: Country vs. Revenue (Top 10)  
- Funnel: Bookings → Cancellations  

### 📄 3️⃣ Customer Insights  
- Pie Chart: Customer Type Split  
- Clustered Column: New vs. Repeat Guests  
- Line Chart: ADR vs. Lead Time  
- Table: Special Requests by Customer Type  

---

## 🧠 Tech Stack  

| Tool | Purpose |
|------|----------|
| **Power BI** | Dashboard design & business analytics |
| **Power Query** | ETL – cleaning & transforming data |
| **DAX** | Calculated measures & KPIs |
| **Excel / CSV (Kaggle)** | Dataset source |

---

## 🧰 ETL Process  

```DAX
// Step 1: Data Loading
Imported Kaggle CSV dataset into Power BI.

// Step 2: Data Cleaning (Power Query)
- Removed nulls and corrected data types
- Handled text inconsistencies in categorical columns
- Added calculated columns:
    Total_Nights = stays_in_weekend_nights + stays_in_week_nights  
    Total_Guests = adults + children + babies  

// Step 3: Data Modeling
Fact Table: hotel_bookings  
Dimension Table: DateTable  
DateTable = CALENDAR(MIN(hotel_bookings[reservation_status_date]), MAX(hotel_bookings[reservation_status_date]))  

Relationship: DateTable[Date] → hotel_bookings[reservation_status_date]

// 📅 Date Table Columns
Year = YEAR(DateTable[Date])  
MonthNumber = MONTH(DateTable[Date])  
MonthName = FORMAT(DateTable[Date], "MMMM")  
MonthYear = FORMAT(DateTable[Date], "MMM YYYY")  
WeekNumber = WEEKNUM(DateTable[Date], 2)
