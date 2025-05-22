# LEETCODE 50-SQL-Solved-Questions


# SQL Query Collection

## 1757 - Recyclable and Low Fat Products

```sql
SELECT product_id
FROM Products
WHERE low_fats = 'Y'
AND recyclable = 'Y';

## https://leetcode.com/problems/investments-in-2016

```
SELECT
    ROUND(SUM(tiv_2016),2) AS tiv_2016
FROM insurance
WHERE tiv_2015 IN (SELECT tiv_2015 FROM insurance GROUP BY tiv_2015 HAVING COUNT(*) > 1)
AND (lat,lon) IN (SELECT lat,lon FROM insurance GROUP BY lat,lon HAVING COUNT(*) = 1)




