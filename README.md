# SQL Interview Questions and Answers


---

## 🧠 Question 1: Retrieve all customers who made a purchase in 2023

```sql
SELECT *
FROM orders
WHERE YEAR(order_date) = 2023;

1757. Recyclable and Low Fat Products
```
SELECT product_id
FROM Products
WHERE low_fats = 'Y'
AND recyclable = 'Y'
