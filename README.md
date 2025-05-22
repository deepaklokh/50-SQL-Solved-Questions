# SQL Interview Questions and Answers


---

## 🧠 Question 1: Retrieve all customers who made a purchase in 2023

```sql
SELECT *
FROM orders
WHERE YEAR(order_date) = 2023;


