# Uber Rides Data Analysis Dashboard

![Power BI](https://img.shields.io/badge/Power_BI-Data_Viz-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Analysis](https://img.shields.io/badge/Methodology-EDA-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

A data analytics project that applies **Business Intelligence (BI)** principles to Uber trip data. This project demonstrates the end-to-end data analysis lifecycle: from raw data extraction to actionable insights via an interactive dashboard.

![Dashboard Preview](uber%20dashboard.PNG)

## 📖 Theoretical Framework

This project is built upon the **Data Analytics Lifecycle**, systematically transforming raw data into business value.

### 1. Requirements Gathering (Business Understanding)
Every analytics project begins with a question. For this dashboard, the theoretical business problem was:
*   *"How can we optimize fleet allocation and reduce booking loss?"*
*   **KPIs Defined**: Revenue, Total Bookings, Booking Success Rate, Average Trip Distance.

### 2. Data Preprocessing (ETL Methodology)
Raw real-world data is rarely ready for analysis. The **ETL (Extract, Transform, Load)** process was applied using Power BI's Query Editor:
*   **Data Cleaning**: Handling missing values (Nulls) and removing duplicate trip records.
*   **Data Transformation**: Converting 'Start Date' and 'End Date' into standardized DateTime formats to enable time-series analysis.
*   **Feature Engineering**: Creating new calculated columns such as `Trip Duration` (End Time - Start Time) to measure efficiency.

### 3. Data Modeling (Star Schema)
To ensure performance and accurate filtering, a **Star Schema** approach was theoretically applied (even if flattened for this specific single-table dataset, the logic follows dimensional modeling):
*   **Fact Table**: Contains quantitative data (Revenue, Distance, Ratings).
*   **Dimension Attributes**: Contains qualitative attributes (Vehicle Type, Date hierarchies, Status).
*   This separation allows for efficient **Slicing and Dicing** of data across different dimensions (e.g., viewing Revenue *by* Month *by* Category).

### 4. Visualization Theory
Charts were selected based on **Visual Perception metrics**:
*   **KPI Cards**: Used for 'Big Numbers' (Revenue, Bookings) to capture immediate attention (Preattentive Processing).
*   **Line Charts**: Chosen for `Revenue over Time` because the human eye is best at detecting trends across continuous X-axes (Dates).
*   **Bar Charts**: Used for `Revenue by Vehicle Type` to allow for easy magnitude comparison between distinct categories.

## 📊 Analytical Insights

| Metric Category | Theoretical Insight | Observed Value |
| :--- | :--- | :--- |
| **Financial Health** | Revenue is the primary indicator of business success. Tracking this against vehicle types identifies high-yield assets. | **$10M Total Revenue** |
| **Operational Efficiency** | The gap between Total and Completed bookings ("Lost Bookings") represents immediate revenue leakage. | **37% Loss Rate** (11K Lost / 30K Total) |
| **Customer Sentiment** | Ratings are a lagging indicator of service quality. High variance between Driver and Customer ratings can indicate platform friction. | **Avg Rating: ~4.0** |

## 📂 Dataset Dictionary

Understanding the columns is crucial for the **Exploratory Data Analysis (EDA)** phase:

| Field | Data Type | Description |
| :--- | :--- | :--- |
| `Date` | Datetime | The timestamp of the trip request. |
| `Category` | Categorical | Business vs. Personal classification. |
| `Start/Stop` | Geospatial | Pickup and Drop-off locations. |
| `Miles` | Numerical | Distance covered per trip. |
| `Purpose` | Categorical | Reason for travel (Meeting, Meal, Commute). |

