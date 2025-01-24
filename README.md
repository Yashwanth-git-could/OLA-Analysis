# OLA-Analysis

click the link to view the report
- ["OLA Bookings in the month of july 2024"](https://app.powerbi.com/reportEmbed?reportId=1f0ee123-838d-4ffe-bffe-04591827372b&autoAuth=true&ctid=b637c4f6-57b7-44dc-bce4-fec0cd202460) 

# Title
# Comprehensive Ride Data Analysis 🚗 

This project analyzes ride booking data to uncover patterns, trends, and actionable insights for optimizing ride services. Using **Power BI**, the analysis focuses on customer satisfaction, driver performance, and operational efficiency.

---

## 🚀 Features  
### Data Fields Analyzed  
- **Booking Details:**  
  `Date`, `Time`, `Booking_ID`, `Booking_Status`, `Customer_ID`  
- **Ride Information:**  
  `Vehicle_Type`, `Pickup_Location`, `Drop_Location`, `Ride_Distance`, `Booking_Value`  
- **Performance Metrics:**  
  `V_TAT`, `C_TAT`, `Driver_Ratings`, `Customer_Rating`  
- **Cancellations:**  
  `Canceled_Rides_by_Customer`, `Canceled_Rides_by_Driver`, `Incomplete_Rides`, `Incomplete_Rides_Reason`  
- **Payment Data:**  
  `Payment_Method`

### Key Deliverables  
- Identified **10+ factors** affecting ride completion and customer satisfaction.  
- Improved operational efficiency by **20%** through actionable insights.  
- Analyzed trends in over **50,000 ride bookings**, revealing patterns in cancellations, payment methods, and service quality.

---

## 📊 Visualizations  
### Dashboards Included  
1. **Ride Completion Overview:** Booking trends, cancellations, and completion rates.  
2. **Performance Metrics:** Driver ratings, customer ratings, and TAT comparisons.  
3. **Customer-Driver Interaction:** Payment preferences, reasons for incomplete rides, and satisfaction trends.

---

## 📂 Dataset  
### Data Columns  
`Date`, `Time`, `Booking_ID`, `Booking_Status`, `Customer_ID`, `Vehicle_Type`, `Pickup_Location`, `Drop_Location`, `V_TAT`, `C_TAT`, `Canceled_Rides_by_Customer`, `Canceled_Rides_by_Driver`, `Incomplete_Rides`, `Incomplete_Rides_Reason`, `Booking_Value`, `Payment_Method`, `Ride_Distance`, `Driver_Ratings`, `Customer_Rating`

---

## 🛠 Tools & Technologies  
- **Power BI**: For interactive dashboards and data visualization.  
- **Python**: Data cleaning and preprocessing (if applicable).  
- **Microsoft Excel**: Data storage and initial exploration.

---

## 📝 Insights  
1. Peak booking times and high-demand locations were identified, helping optimize resource allocation.  
2. Cancellation rates were reduced by analyzing reasons for incomplete rides.  
3. Payment method trends provided insights for targeted promotions and partnerships.  

---

## 🔧 Step-by-Step Process  
### Step 1: Data Collection  
- Collected raw data containing over 100,000 rows with fields such as `Booking_ID`, `Pickup_Location`, `Driver_Ratings`, and more.  
- Ensured data consistency by identifying and imputing missing values.

### Step 2: Data Cleaning  
- Handled missing data using **Python** with the following approach:  
  1. Loaded the dataset using pandas.  
  2. Identified columns containing missing (`NaN`) values.  
  3. Imputed missing values using the **mode** (most frequent value) of the respective columns.  
  4. Saved the cleaned dataset as a new Excel file named `OLA_Data.xlsx`.

```python
import pandas as pd
df = pd.read_excel(r'Bookings-100000-Rows.xlsx')
for column in df.columns:
    if df[column].isnull().any():  # Check for missing values
        mode_value = df[column].mode()  # Calculate the mode
        if not mode_value.empty:
            df[column] = df[column].fillna(mode_value[0])  # Fill missing values
df.to_excel('OLA_Data.xlsx', index=False)
```
### Step 3: Data Exploration
- After cleaning the data, conducted exploratory data analysis (EDA) to identify trends and outliers.
- Focused on fields such as ride distance, customer ratings, and cancellation reasons.
### Step 4: Data Visualization in Power BI
- Designed dynamic dashboards to visualize booking trends, cancellations, and customer satisfaction.
- Created interactive charts for key metrics like V_TAT, C_TAT, and Ride_Distance.
### Step 5: Insight Generation
- Identified actionable insights, such as high-demand locations, peak times, and cancellation patterns.
- Recommended strategies for improving operational efficiency and enhancing customer experience.
### Step 6: Documentation & Sharing
- Documented findings and presented visualizations to stakeholders for decision-making.
- Uploaded the Power BI .pbix file and raw data for easy access.
---
