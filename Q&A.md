Here’s a list of **scenario-based questions** for each tool—Power BI, SQL, and Excel—along with answers to illustrate the analysis for the given fields.

---

## **Power BI Questions**

1. **What is the total revenue generated over a specific date range?**
   - **Answer**: Use the `Booking_Value` field and a slicer/filter on the `Date` column to calculate total revenue using a card visualization.

2. **Which `Vehicle_Type` has the highest number of bookings?**
   - **Answer**: Create a bar chart with `Vehicle_Type` on the x-axis and count of `Booking_ID` on the y-axis to identify the most popular vehicle type.

3. **What is the average `Driver_Ratings` and `Customer_Rating` by `Pickup_Location`?**
   - **Answer**: Use a table or matrix visualization with `Pickup_Location` as rows, and `Driver_Ratings` and `Customer_Rating` as values with the average aggregation.

4. **What is the trend of `Canceled_Rides_by_Customer` over time?**
   - **Answer**: Use a line chart with `Date` on the x-axis and `Canceled_Rides_by_Customer` as the value to visualize the trend.

5. **Which `Payment_Method` is most commonly used for rides?**
   - **Answer**: Create a pie chart or bar chart showing the distribution of `Payment_Method` values.

6. **Which reasons (`Incomplete_Rides_Reason`) are most responsible for incomplete rides?**
   - **Answer**: Use a bar chart to count the occurrences of each value in the `Incomplete_Rides_Reason` column.

7. **Which `Customer_ID` has the highest booking value?**
   - **Answer**: Use a table or matrix with `Customer_ID` as rows and `Booking_Value` as values, sorted in descending order.

---

## **SQL Questions**

1. **What is the total number of rides completed?**
   ```sql
   SELECT COUNT(*) AS Total_Rides
   FROM BookingTable
   WHERE Booking_Status = 'Completed';
   ```
   - **Answer**: Returns the total number of completed rides.

2. **Which `Customer_ID` has canceled the most rides?**
   ```sql
   SELECT Customer_ID, SUM(Canceled_Rides_by_Customer) AS Total_Cancelled
   FROM BookingTable
   GROUP BY Customer_ID
   ORDER BY Total_Cancelled DESC
   LIMIT 1;
   ```
   - **Answer**: Returns the customer with the highest canceled rides.

3. **What is the average ride distance (`Ride_Distance`) for each vehicle type?**
   ```sql
   SELECT Vehicle_Type, AVG(Ride_Distance) AS Avg_Distance
   FROM BookingTable
   GROUP BY Vehicle_Type;
   ```
   - **Answer**: Shows the average ride distance for each vehicle type.

4. **What is the total `Booking_Value` for each `Payment_Method`?**
   ```sql
   SELECT Payment_Method, SUM(Booking_Value) AS Total_Value
   FROM BookingTable
   GROUP BY Payment_Method;
   ```
   - **Answer**: Provides total booking value split by payment methods.

5. **Which `Pickup_Location` has the highest number of incomplete rides?**
   ```sql
   SELECT Pickup_Location, COUNT(*) AS Incomplete_Rides
   FROM BookingTable
   WHERE Booking_Status = 'Incomplete'
   GROUP BY Pickup_Location
   ORDER BY Incomplete_Rides DESC
   LIMIT 1;
   ```
   - **Answer**: Identifies the pickup location with the most incomplete rides.

6. **What is the average time taken (`C_TAT`) for rides?**
   ```sql
   SELECT AVG(C_TAT) AS Avg_Time_Taken
   FROM BookingTable;
   ```
   - **Answer**: Displays the average time taken across all rides.

7. **Which driver has the highest average `Driver_Ratings`?**
   ```sql
   SELECT Driver_ID, AVG(Driver_Ratings) AS Avg_Rating
   FROM BookingTable
   GROUP BY Driver_ID
   ORDER BY Avg_Rating DESC
   LIMIT 1;
   ```
   - **Answer**: Finds the driver with the highest average rating.

---

## **Excel Questions**

1. **What is the total revenue (`Booking_Value`) in Excel?**
   - **Answer**: Use the `SUM` function on the `Booking_Value` column: `=SUM(Booking_Value)`.

2. **How can you calculate the average `Ride_Distance` for completed rides?**
   - **Answer**: Use a conditional average with `AVERAGEIF`:
     `=AVERAGEIF(Booking_Status, "Completed", Ride_Distance)`.

3. **What is the distribution of `Payment_Method`?**
   - **Answer**: Create a pivot table with `Payment_Method` as rows and count `Booking_ID` to see the distribution.

4. **How can you find the most frequent `Incomplete_Rides_Reason`?**
   - **Answer**: Use a pivot table with `Incomplete_Rides_Reason` as rows and count `Booking_ID`, then sort by count in descending order.

5. **How to calculate the percentage of rides canceled by customers?**
   - **Answer**: Divide the sum of `Canceled_Rides_by_Customer` by the total rides:
     `=SUM(Canceled_Rides_by_Customer)/COUNTA(Booking_ID)*100`.

6. **How to identify the highest-rated driver?**
   - **Answer**: Use the `MAX` function on `Driver_Ratings` and match it with the driver name using `INDEX-MATCH`.

7. **How can you visualize the monthly trend of incomplete rides?**
   - **Answer**: Create a pivot table with `Date` grouped by months and `Incomplete_Rides` summed, then insert a line chart.

---