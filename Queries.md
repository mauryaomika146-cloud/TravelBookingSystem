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
SELECT Customer.Name, Booking.Booking_ID, Booking.Travel_Date
FROM Customer 
JOIN Booking ON Customer.Customer_ID = Booking.Customer_ID;
```

```sql
5. Show package details with booking
SELECT Package.Package_Name, Booking.Booking_ID
FROM Package 
JOIN Booking ON Package.Package_ID = Booking.Package_ID;
```

```sql
6. Show agent handling bookings
SELECT Agent.Name AS Agent_Name, Booking.Booking_ID
FROM Agent 
JOIN Booking ON Agent.Agent_ID = Booking.Agent_ID;
```

```sql
7. Total revenue (sum of payments)
SELECT SUM(Amount) AS Total_Revenue FROM Payment;
```

```sql
8. Customers who booked Goa trip
SELECT Customer.Name
FROM Customer 
JOIN Booking ON Customer.Customer_ID = Booking.Customer_ID
JOIN Package ON Booking.Package_ID = Package.Package_ID
WHERE Package.Destination = 'Goa';
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
Customer.Name,
Package.Package_Name,
Agent.Name AS Agent_Name,
Booking.Total_Amount
FROM Booking
JOIN Customer ON Booking.Customer_ID = Customer.Customer_ID
JOIN Package ON Booking.Package_ID = Package.Package_ID
JOIN Agent ON Booking.Agent_ID = Agent.Agent_ID;
```
