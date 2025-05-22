# LEETCODE 50-SQL-Solved-Questions


# SQL Query Collection

## 1757 - Recyclable and Low Fat Products

```sql
SELECT product_id
FROM Products
WHERE low_fats = 'Y'
AND recyclable = 'Y';

584 - Find Customer Referee
sql
Copy
Edit
SELECT name 
FROM Customer 
WHERE referee_id != 2 OR referee_id IS null;


