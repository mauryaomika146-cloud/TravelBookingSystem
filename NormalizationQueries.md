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
