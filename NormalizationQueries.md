## NormalizationQueries
## Find how many times each customer appears in the UNF table.
```sql
 SELECT Customer_Name, COUNT(*)
    -> FROM UNF_BOOKING
    -> GROUP BY Customer_Name;
```

## Output 
```sql
+---------------+----------+
| Customer_Name | COUNT(*) |
+---------------+----------+
| Omika         |        2 |
| Shreya        |        1 |
+---------------+----------+
2 rows in set (0.001 sec)
```

## Check if customer names are duplicated in the Customer table.
```sql
SELECT Name, COUNT(*)
    -> FROM Customer
    -> GROUP BY Name;
```

## Output
```sql
+--------+----------+
| Name   | COUNT(*) |
+--------+----------+
| Omika  |        1 |
| Shreya |        1 |
+--------+----------+
2 rows in set (0.017 sec)
```

## Retrieve customer name, package name, and booking date using JOIN.
```sql
SELECT c.Name, p.Package_Name, b.Booking_Date
    -> FROM Booking b
    -> JOIN Customer c ON b.Customer_ID = c.Customer_ID
    -> JOIN Package p ON b.Package_ID = p.Package_ID;
```
## Output
```sql
+-------+--------------+--------------+
| Name  | Package_Name | Booking_Date |
+-------+--------------+--------------+
| Omika | Goa Trip     | 2025-02-01   |
+-------+--------------+--------------+
1 row in set (0.020 sec)
```

## Find total number of bookings done by each customer.
```sql
ELECT c.Name, COUNT(b.Booking_ID) AS Total_Bookings
    -> FROM Customer c
    -> JOIN Booking b ON c.Customer_ID = b.Customer_ID
    -> GROUP BY c.Name;
```

## Output
```sql
+-------+----------------+
| Name  | Total_Bookings |
+-------+----------------+
| Omika |              1 |
+-------+----------------+
1 row in set (0.017 sec)
```

## Calculate total revenue from all bookings.
```sql
SELECT SUM(Total_Amount) AS Total_Revenue
    -> FROM Booking;
```

## Output
```sql
+---------------+
| Total_Revenue |
+---------------+
|      30000.00 |
+---------------+
1 row in set (0.001 sec)
```
