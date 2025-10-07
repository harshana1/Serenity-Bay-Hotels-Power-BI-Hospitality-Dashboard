# 🏨 Serenity Bay Hotels – Power BI Hospitality Dashboard  

🚀 **Power BI Project | Hospitality Analytics | End-to-End Dashboard**

This project analyzes real hotel booking data to uncover insights into **revenue performance**, **occupancy trends**, and **guest behavior** in the hospitality industry.  
Built using the **Hotel Bookings dataset from Kaggle**, it demonstrates how data analytics can drive smarter business decisions in the hotel sector.

---

## 📊 Project Overview  

**Objective:**  
To design a Power BI dashboard that provides executives with actionable insights into hotel performance, cancellations, and customer demographics.

**Business Problem:**  
Hotel managers need to understand key metrics such as:
- How occupancy and revenue fluctuate across months  
- What drives cancellations  
- Which customer segments and countries contribute most to bookings  

---

## 🧩 Key Features  

✅ **ETL with Power Query** – Cleaned and transformed raw Kaggle data  
✅ **Data Modeling** – Created relationships between fact & date tables  
✅ **Custom DAX Measures** – Built KPIs like ADR, RevPAR, Occupancy %, and Cancellation Rate  
✅ **Dynamic Slicers & Filters** – Hotel Type, Year, Month, Market Segment, Country  
✅ **Interactive Navigation Buttons** – For a professional multi-page dashboard  
✅ **Three Dashboard Pages**  

---

## 📁 Dashboard Pages  

### 📄 1. Executive Overview  
- KPIs: Total Revenue, ADR, RevPAR, Occupancy %, Cancellation %  
- Line Chart: Revenue & Occupancy by Month-Year  
- Pie Chart: Bookings vs. Cancellations  

### 📄 2. Revenue & Booking Analysis  
- Column Chart: Revenue by Market Segment  
- Bar Chart: Revenue by Reserved Room Type  
- Table: Country vs. Revenue (Top 10)  
- Funnel: Bookings → Cancellations  

### 📄 3. Customer Insights  
- Pie Chart: Customer Type Split  
- Column Chart: New vs. Repeat Guests  
- Line Chart: ADR vs. Lead Time  
- Table: Special Requests by Customer Type  

---

## 🧠 Tech Stack  

| Tool | Purpose |
|------|----------|
| **Power BI** | Dashboard design & visualization |
| **Power Query** | Data cleaning & transformation |
| **DAX** | Business metrics and calculations |
| **Excel / CSV (Kaggle)** | Data source |

---

## 🧮 Key DAX Measures  

```DAX
Total Bookings = COUNTROWS(hotel_bookings)

Total Revenue = SUM(hotel_bookings[adr] * hotel_bookings[Total_Nights])

ADR = DIVIDE([Total Revenue], [Total Bookings])

Occupancy Rate = DIVIDE([Total Nights], SUM(hotel_bookings[adults]))

RevPAR = [ADR] * [Occupancy Rate]

Cancellation Rate = DIVIDE(CALCULATE(COUNTROWS(hotel_bookings), hotel_bookings[is_canceled] = 1), [Total Bookings])
