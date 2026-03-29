##Queries 

```sql
1. Show all customers
SELECT * FROM Customer;
```

```sql
2. Show all packages
SELECT * FROM Package;
```

```sql
3. Show all bookings
SELECT * FROM Booking;
```

```sql
4. Show customer names with their bookings
SELECT c.Name, b.Booking_ID, b.Travel_Date
FROM Customer c
JOIN Booking b ON c.Customer_ID = b.Customer_ID;
```

```sql
5. Show package details with booking
SELECT p.Package_Name, b.Booking_ID
FROM Package p
JOIN Booking b ON p.Package_ID = b.Package_ID;
```

```sql
6. Show agent handling bookings
SELECT a.Name AS Agent_Name, b.Booking_ID
FROM Agent a
JOIN Booking b ON a.Agent_ID = b.Agent_ID;
```

```sql
7. Total revenue (sum of payments)
SELECT SUM(Amount) AS Total_Revenue FROM Payment;
```

```sql
8. Customers who booked Goa trip
SELECT c.Name
FROM Customer c
JOIN Booking b ON c.Customer_ID = b.Customer_ID
JOIN Package p ON b.Package_ID = p.Package_ID
WHERE p.Destination = 'Goa';
```

```sql
9. Count total bookings
SELECT COUNT(*) AS Total_Bookings FROM Booking;
```

```sql
10. Show payment status
SELECT Booking_ID, Payment_Status FROM Payment;
```

```sql
11. Show bookings above 20000
SELECT * FROM Booking WHERE Total_Amount > 20000;
```

```sql
12. Update payment status
UPDATE Payment
SET Payment_Status = 'Completed'
WHERE Payment_ID = 1;
```

```sql
13. Delete a booking
DELETE FROM Booking WHERE Booking_ID = 2;
```

```sql
14. Find most expensive package
SELECT * FROM Package
ORDER BY Price DESC
LIMIT 1;
```

```sql
15. Show full booking details (JOIN ALL)
SELECT 
    c.Name AS Customer,
    p.Package_Name,
    a.Name AS Agent,
    b.Travel_Date,
    pay.Amount
FROM Booking b
JOIN Customer c ON b.Customer_ID = c.Customer_ID
JOIN Package p ON b.Package_ID = p.Package_ID
JOIN Agent a ON b.Agent_ID = a.Agent_ID
JOIN Payment pay ON b.Booking_ID = pay.Booking_ID;
```
