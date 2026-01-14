# 🚗 Ola Ride Analytics Dashboard

<div align="center">

![SQL](https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Status](https://img.shields.io/badge/Status-Complete-success?style=for-the-badge)

**End-to-end ride-hailing data analysis combining SQL analytics with interactive Power BI visualizations**

[Key Insights](#-key-insights) • [SQL Analysis](#-sql-analysis) • [Dashboard](#-power-bi-dashboard) • [Setup](#-getting-started)

</div>

---

## 🎯 Project Overview

This project analyzes **Ola's ride-booking data** to uncover operational insights, customer behavior patterns, and performance metrics. The analysis pipeline combines:

- 🗃️ **SQL Analytics** – Data extraction, transformation & view creation
- 📊 **Power BI Dashboard** – Interactive visualizations & KPI tracking

---

## 📌 Key Insights

### 📈 Business Metrics Analyzed

| Category | Metrics |
|----------|---------|
| **Booking Performance** | Total rides, Success rate, Cancellation patterns |
| **Revenue Analysis** | Total booking value, Successful ride value |
| **Vehicle Insights** | Average ride distance by vehicle type |
| **Customer Behavior** | Top customers, Rating patterns, Payment preferences |
| **Driver Performance** | Driver ratings, Cancellation reasons |

---

## 🔍 SQL Analysis

### Views Created for Analysis

| View Name | Purpose |
|-----------|---------|
| `Successful_Bookings` | All completed rides |
| `ride_distance_for_each_vehicle` | Avg distance by vehicle type |
| `cancelled_rides_by_customers` | Customer cancellation count |
| `Top_5_Customers` | Highest booking customers |
| `Rides_Canceled_by_drivers_P_C_Issues` | Driver cancellations (personal/car issues) |
| `Max_Min_Driver_Rating` | Prime Sedan rating range |
| `UPI_Payment` | UPI transaction rides |
| `AVG_Cost_Rating` | Customer rating by vehicle |
| `total_successful_ride_value` | Revenue from successful rides |
| `Incomplete_Rides_Reason` | Incomplete ride analysis |

### Sample Queries

```sql
-- Top 5 Customers by Ride Count
SELECT Customer_ID, COUNT(Booking_ID) AS total_rides
FROM bookings
GROUP BY Customer_ID
ORDER BY total_rides DESC LIMIT 5;

-- Average Distance by Vehicle Type
SELECT Vehicle_Type, AVG(Ride_Distance) AS avg_distance 
FROM bookings 
GROUP BY Vehicle_Type;

-- Total Revenue from Successful Rides
SELECT SUM(Booking_Value) AS total_successful_ride_value
FROM bookings
WHERE Booking_Status = 'Success';
```

---

## 📊 Power BI Dashboard

### Dashboard Features

```
┌─────────────────────────────────────────────────────────────────┐
│                    🚗 OLA ANALYTICS DASHBOARD                   │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  📈 BOOKING METRICS          │  🚙 VEHICLE PERFORMANCE         │
│  • Total Bookings            │  • Distance by Vehicle Type      │
│  • Success Rate              │  • Ratings by Category           │
│  • Cancellation Breakdown    │  • Popular Vehicle Types         │
│                              │                                  │
│  👥 CUSTOMER INSIGHTS        │  💳 PAYMENT ANALYSIS            │
│  • Top Customers             │  • Payment Method Distribution   │
│  • Rating Distribution       │  • UPI vs Other Methods          │
│  • Booking Patterns          │  • Revenue by Payment Type       │
│                              │                                  │
│  🚨 OPERATIONAL METRICS      │  ⭐ RATINGS OVERVIEW            │
│  • Incomplete Rides          │  • Driver Ratings                │
│  • Cancellation Reasons      │  • Customer Ratings              │
│  • Driver Issues Tracking    │  • Rating Trends                 │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### Key Visualizations

| Chart Type | Insight |
|------------|---------|
| 📊 **Bar Charts** | Vehicle type comparison, Top customers |
| 🥧 **Pie Charts** | Booking status distribution, Payment methods |
| 📈 **KPI Cards** | Total bookings, Revenue, Success rate |
| 📋 **Tables** | Detailed ride records, Incomplete ride reasons |

---

## 📂 Dataset Schema

| Column | Description |
|--------|-------------|
| `Booking_ID` | Unique booking identifier |
| `Customer_ID` | Customer identifier |
| `Vehicle_Type` | Type of vehicle (Prime Sedan, Mini, Auto, etc.) |
| `Booking_Status` | Success / Canceled by Customer / Canceled by Driver |
| `Ride_Distance` | Distance traveled (km) |
| `Booking_Value` | Fare amount |
| `Payment_Method` | UPI / Cash / Card / Wallet |
| `Driver_Ratings` | Rating given to driver (1-5) |
| `Customer_Rating` | Rating given by driver (1-5) |
| `Canceled_Rides_by_Driver` | Cancellation reason |
| `Incomplete_Rides` | Yes/No flag |
| `Incomplete_Rides_Reason` | Reason for incomplete ride |

---

## 🚀 Getting Started

### Prerequisites

- **MySQL** 8.0+ or compatible database
- **Power BI Desktop** (for dashboard)
- Ola bookings dataset (CSV format)

### Setup Instructions

1. **Database Setup**
   ```sql
   CREATE DATABASE IF NOT EXISTS ola;
   USE ola;
   -- Import your bookings data into 'bookings' table
   ```

2. **Run SQL Analysis**
   ```bash
   # Execute the SQL script to create all views
   mysql -u username -p ola < "Ola Project sql.sql"
   ```

3. **Open Power BI Dashboard**
   ```
   Open "Ola project power BI 1.pbix" in Power BI Desktop
   ```

4. **Connect Data Source**
   - Update MySQL connection settings in Power BI
   - Refresh data to load latest bookings

---

## 💡 Business Applications

| Use Case | Benefit |
|----------|---------|
| **Operations Optimization** | Identify peak cancellation times & reasons |
| **Customer Retention** | Recognize top customers for loyalty programs |
| **Driver Management** | Track driver performance & issue patterns |
| **Revenue Analysis** | Monitor booking value trends |
| **Service Quality** | Analyze ratings to improve customer experience |

---

## 🛠️ Tech Stack

<div align="center">

| Component | Technology |
|-----------|------------|
| Database | ![MySQL](https://img.shields.io/badge/MySQL-005C84?style=flat-square&logo=mysql&logoColor=white) |
| Visualization | ![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat-square&logo=powerbi&logoColor=black) |
| Query Language | ![SQL](https://img.shields.io/badge/SQL-336791?style=flat-square&logo=postgresql&logoColor=white) |

</div>

---

## 📈 Future Enhancements

- [ ] Real-time data pipeline integration
- [ ] Predictive analytics for demand forecasting
- [ ] Driver-customer matching optimization
- [ ] Surge pricing analysis
- [ ] Geographic heatmap visualizations

---

## 🤝 Contributing

Contributions are welcome! Feel free to submit issues or pull requests.

---

## 📄 License

This project is licensed under the MIT License.

---

<div align="center">

**⭐ Star this repository if you found it helpful!**

Built with 💛 for data-driven ride analytics

</div>
