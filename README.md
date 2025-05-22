LeetCode Top SQL 50 - Questions and Answers
A comprehensive collection of solutions for the SQL 50 Study Plan on LeetCode

Table of Contents
1757. Recyclable and Low Fat Products
584. Find Customer Referee
595. Big Countries
1148. Article Views I
1683. Invalid Tweets
1378. Replace Employee ID With The Unique Identifier
1068. Product Sales Analysis I
1581. Customer Who Visited but Did Not Make Any Transactions
197. Rising Temperature
1661. Average Time of Process per Machine
577. Employee Bonus
1280. Students and Examinations
570. Managers with at Least 5 Direct Reports
1934. Confirmation Rate
620. Not Boring Movies
1251. Average Selling Price
1075. Project Employees I
1633. Percentage of Users Attended a Contest
1211. Queries Quality and Percentage
1193. Monthly Transactions I
1174. Immediate Food Delivery II
550. Game Play Analysis IV
2356. Number of Unique Subjects Taught by Each Teacher
1141. User Activity for the Past 30 Days I
1070. Product Sales Analysis III
596. Classes More Than 5 Students
1729. Find Followers Count
619. Biggest Single Number
1045. Customers Who Bought All Products
1731. The Number of Employees Which Report to Each Employee
1789. Primary Department for Each Employee
610. Triangle Judgement
180. Consecutive Numbers
1164. Product Price at a Given Date
1978. Employees Whose Manager Left the Company
185. Department Top Three Salaries
1667. Fix Names in a Table
1527. Patients With a Condition
196. Delete Duplicate Emails
176. Second Highest Salary
1517. Find Users With Valid E-Mails
1204. Last Person to Fit in the Bus
1907. Count Salary Categories
626. Exchange Seats
1327. List the Products Ordered in a Period
1484. Group Sold Products By The Date
1341. Movie Rating
1321. Restaurant Growth
602. Friend Requests II: Who Has the Most Friends
585. Investments in 2016
1757. Recyclable and Low Fat Products
View on LeetCode

SELECT product_id
FROM Products
WHERE low_fats = 'Y'
AND recyclable = 'Y'
This query selects product IDs where both low_fats and recyclable values are 'Y'.

584. Find Customer Referee
View on LeetCode

SELECT name 
FROM Customer 
WHERE referee_id != 2 OR referee_id IS null
This query returns the names of customers who weren't referred by customer with id = 2 or weren't referred at all (NULL referee_id).

595. Big Countries
View on LeetCode

SELECT name, population, area
FROM WORLD
WHERE area >= 3000000
OR population >= 25000000
This query selects countries that are considered "big" - either having an area of at least 3 million square km or a population of at least 25 million.

1148. Article Views I
View on LeetCode

SELECT DISTINCT author_id as id
FROM Views
WHERE viewer_id >= 1
AND author_id = viewer_id
ORDER BY author_id
This query finds the IDs of authors who have viewed their own articles. It returns distinct author IDs in ascending order.

1683. Invalid Tweets
View on LeetCode

SELECT tweet_id
FROM Tweets
WHERE length(content) > 15
This query finds tweet IDs where the content length exceeds 15 characters, which are considered invalid tweets.

1378. Replace Employee ID With The Unique Identifier
View on LeetCode

SELECT unique_id, name
FROM Employees e
LEFT JOIN EmployeeUNI eu
ON e.id = eu.id
This query performs a LEFT JOIN to match employees with their unique identifiers, preserving all employee records even if they don't have a unique identifier.

1068. Product Sales Analysis I
View on LeetCode

SELECT product_name, year, price
FROM Sales s
LEFT JOIN Product p
ON s.product_id = p.product_id
This query joins the Sales and Product tables to show product_name, year, and price for each sale.

1581. Customer Who Visited but Did Not Make Any Transactions
View on LeetCode

SELECT customer_id, COUNT(*) as count_no_trans
FROM Visits 
WHERE visit_id NOT IN (SELECT DISTINCT visit_id FROM Transactions)
GROUP BY customer_id
This query finds customers who visited but didn't make any transactions, counting the number of such visits for each customer.

197. Rising Temperature
View on LeetCode

SELECT w1.id 
FROM Weather w1, Weather w2
WHERE DATEDIFF(w1.recordDate, w2.recordDate) = 1
AND w1.temperature > w2.temperature
Alternative solution:

SELECT w1.id
FROM Weather w1, Weather w2
WHERE w1.temperature > w2.temperature
AND SUBDATE(w1.recordDate, 1) = w2.recordDate
This query finds weather records where the temperature is higher than the previous day's temperature.

1661. Average Time of Process per Machine
View on LeetCode

SELECT machine_id, ROUND(AVG(end - start), 3) AS processing_time
FROM 
(SELECT machine_id, process_id, 
    MAX(CASE WHEN activity_type = 'start' THEN timestamp END) AS start,
    MAX(CASE WHEN activity_type = 'end' THEN timestamp END) AS end
 FROM Activity 
  GROUP BY machine_id, process_id) AS subq
GROUP BY machine_id
This query calculates the average processing time for each machine by first grouping start and end timestamps for each process, then calculating the average time difference.

577. Employee Bonus
View on LeetCode

SELECT name, bonus
FROM Employee e
LEFT JOIN Bonus b
ON e.empId = b.empId
WHERE bonus < 1000
OR bonus IS NULL
This query finds employees who received a bonus of less than 1000 or no bonus at all.

1280. Students and Examinations
View on LeetCode

SELECT a.student_id, a.student_name, b.subject_name, COUNT(c.subject_name) AS attended_exams
FROM Students a
JOIN Subjects b
LEFT JOIN Examinations c
ON a.student_id = c.student_id
AND b.subject_name = c.subject_name
GROUP BY 1, 3
ORDER BY 1, 3
This query generates a report showing the number of times each student attended each exam, including zero counts for subjects they didn't attend.

570. Managers with at Least 5 Direct Reports
View on LeetCode

SELECT name 
FROM Employee 
WHERE id IN
  (SELECT managerId 
   FROM Employee 
   GROUP BY managerId 
   HAVING COUNT(*) >= 5
  )
Alternative solution:

SELECT a.name
FROM Employee a
JOIN Employee b
WHERE a.id = b.managerId
GROUP BY b.managerId
HAVING COUNT(*) >= 5
This query finds managers who have at least 5 direct reports.

1934. Confirmation Rate
View on LeetCode

SELECT 
  s.user_id, 
  ROUND(
    COALESCE(
      SUM(
        CASE WHEN ACTION = 'confirmed' THEN 1 END
      ) / COUNT(*), 0),2) 
  AS confirmation_rate 
FROM Signups s 
LEFT JOIN Confirmations c 
ON s.user_id = c.user_id 
GROUP BY s.user_id;
This query calculates the confirmation rate for each user, which is the number of 'confirmed' actions divided by the total number of confirmation requests.

620. Not Boring Movies
View on LeetCode

SELECT *
FROM Cinema
WHERE id % 2 <> 0 
AND description <> "boring"
ORDER BY rating DESC
This query selects movies with odd IDs and a non-boring description, sorted by rating in descending order.

1251. Average Selling Price
View on LeetCode

SELECT p.product_id, 
  ROUND(SUM(price * units) / SUM(units), 2) AS average_price
FROM Prices p
LEFT JOIN UnitsSold s
ON p.product_id = s.product_id
AND purchase_date BETWEEN start_date AND end_date
GROUP BY p.product_id
This query calculates the average selling price for each product, considering only sales that occurred during valid price periods.

1075. Project Employees I
View on LeetCode

SELECT project_id, ROUND(AVG(experience_years), 2) average_years
FROM Project p 
LEFT JOIN Employee e
ON p.employee_id = e.employee_id
GROUP BY project_id
This query calculates the average years of experience for employees working on each project.

1633. Percentage of Users Attended a Contest
View on LeetCode

SELECT r.contest_id,
       ROUND(COUNT(DISTINCT r.user_id) * 100 / (SELECT COUNT(DISTINCT user_id) FROM Users), 2) AS percentage
FROM Register r
GROUP BY r.contest_id
ORDER BY percentage DESC, r.contest_id ASC;
This query calculates the percentage of users who registered for each contest, ordering results by percentage (descending) and contest ID (ascending).

1211. Queries Quality and Percentage
View on LeetCode

SELECT query_name, 
    ROUND(AVG(rating/position), 2) AS quality, 
    ROUND(SUM(IF(rating < 3, 1, 0)) * 100/ COUNT(rating), 2) AS poor_query_percentage
FROM Queries
GROUP BY query_name
Alternative solution:

SELECT query_name, 
    ROUND(AVG(rating/position), 2) AS quality, 
    ROUND(SUM(
        CASE WHEN rating < 3 THEN 1 ELSE 0 END
    ) * 100/ COUNT(rating), 2) AS poor_query_percentage
FROM Queries
GROUP BY query_name
This query calculates query quality metrics: the quality (avg of rating/position) and the percentage of poor queries (rating < 3).

1193. Monthly Transactions I
View on LeetCode

SELECT DATE_FORMAT(trans_date, '%Y-%m') month, country, 
        COUNT(state) trans_count, 
        SUM(IF(state = 'approved', 1, 0)) approved_count, 
        SUM(amount) trans_total_amount,
        SUM(IF(state = 'approved', amount, 0)) approved_total_amount
FROM Transactions
GROUP BY 1, 2
Alternative solution:

SELECT DATE_FORMAT(trans_date, '%Y-%m') month, country, 
        COUNT(state) trans_count, 
        SUM(CASE WHEN state = 'approved' THEN 1 ELSE 0 END) approved_count, 
        SUM(amount) trans_total_amount,
        SUM(CASE WHEN state = 'approved' THEN amount ELSE 0 END) approved_total_amount
FROM Transactions
GROUP BY 1, 2
This query summarizes transaction data by month and country, including counts and amounts for both total and approved transactions.

1174. Immediate Food Delivery II
View on LeetCode

SELECT
    ROUND((COUNT(CASE WHEN d.order_date = d.customer_pref_delivery_date THEN 1 END) / COUNT(*)) * 100, 2)  immediate_percentage
FROM Delivery d
WHERE d.order_date = (
    SELECT
    MIN(order_date)
    FROM Delivery
    WHERE customer_id = d.customer_id
    );
Alternative solution:

SELECT ROUND(AVG(temp.order_date=temp.customer_pref_delivery_date) * 100, 2) immediate_percentage
FROM (
    SELECT *, RANK() OVER(partition by customer_id ORDER BY order_date) od
    FROM Delivery) temp
WHERE temp.od = 1
This query calculates the percentage of first-time orders that were immediate (where preferred delivery date equals order date).

550. Game Play Analysis IV
View on LeetCode

WITH login_date AS (SELECT player_id, MIN(event_date) AS first_login
FROM Activity
GROUP BY player_id),

recent_login AS (
SELECT *, DATE_ADD(first_login, INTERVAL 1 DAY) AS next_day
FROM login_date)

SELECT ROUND((SELECT COUNT(DISTINCT(player_id))
FROM Activity
WHERE (player_id, event_date) IN 
(SELECT player_id, next_day FROM recent_login)) / (SELECT COUNT(DISTINCT player_id) FROM Activity), 2) AS fraction
This query finds the fraction of players who logged in again on the day after their first login.

2356. Number of Unique Subjects Taught by Each Teacher
View on LeetCode

SELECT teacher_id, COUNT(DISTINCT subject_id) cnt
FROM Teacher
GROUP BY teacher_id
This query counts the number of unique subjects taught by each teacher.

1141. User Activity for the Past 30 Days I
View on LeetCode

SELECT activity_date as day, COUNT(DISTINCT user_id) AS active_users
FROM Activity
WHERE activity_date BETWEEN DATE_SUB('2019-07-27', INTERVAL 29 DAY) AND '2019-07-27'
GROUP BY activity_date
This query counts the number of active users for each day within a 30-day period ending on '2019-07-27'.

1070. Product Sales Analysis III
View on LeetCode

SELECT s.product_id, s.year AS first_year, s.quantity, s.price
FROM Sales s
JOIN (
  SELECT product_id, MIN(year) AS year 
  FROM sales 
  GROUP BY product_id
  ) p
ON s.product_id = p.product_id
AND s.year = p.year
Alternative solution:

WITH first_year_sales AS (
  SELECT s.product_id, MIN(s.year) as first_year
  FROM Sales s
  INNER JOIN Product p
  ON s.product_id = p.product_id
  GROUP BY s.product_id)
SELECT f.product_id, f.first_year, s.quantity, s.price
FROM first_year_sales f
JOIN Sales s 
ON f.product_id = s.product_id
AND f.first_year = s.year
This query finds the first year of sales for each product and returns the quantity and price from that year.

596. Classes More Than 5 Students
View on LeetCode

SELECT class
FROM Courses
GROUP BY class
HAVING COUNT(student) >= 5
This query finds classes that have at least 5 students.

1729. Find Followers Count
View on LeetCode

SELECT user_id, COUNT(DISTINCT follower_id) AS followers_count
FROM Followers
GROUP BY user_id
ORDER BY user_id ASC
This query counts the number of followers for each user and orders the results by user_id.

619. Biggest Single Number
View on LeetCode

SELECT COALESCE(
  (SELECT num
  FROM MyNumbers
  GROUP BY num
  HAVING COUNT(num) = 1
  ORDER BY num DESC
  LIMIT 1), null) 
  AS num
This query finds the largest number that appears only once in the table, returning null if there is no such number.

1045. Customers Who Bought All Products
View on LeetCode

SELECT customer_id
FROM Customer
GROUP BY customer_id
HAVING COUNT(DISTINCT product_key) = (
  SELECT COUNT(product_key)
  FROM Product
)
This query finds customers who have purchased every product available in the Product table.

1731. The Number of Employees Which Report to Each Employee
View on LeetCode

SELECT e1.employee_id, e1.name, COUNT(e2.employee_id) reports_count, ROUND(AVG(e2.age)) average_age 
FROM Employees e1, Employees e2
WHERE e1.employee_id = e2.reports_to
GROUP BY e1.employee_id
HAVING reports_count > 0
ORDER BY e1.employee_id
This query finds managers, counts their direct reports, and calculates the average age of those reports.

1789. Primary Department for Each Employee
View on LeetCode

SELECT employee_id, department_id
FROM Employee 
WHERE primary_flag = 'Y'
UNION
SELECT employee_id, department_id
FROM Employee
GROUP BY employee_id
HAVING COUNT(employee_id)=1
Alternative solution:

SELECT employee_id,department_id
FROM Employee
WHERE primary_flag = 'Y' OR employee_id IN
    (SELECT employee_id
     FROM employee
     GROUP BY employee_id
     HAVING COUNT(department_id) = 1
    )
This query identifies the primary department for each employee, considering both primary_flag and single-department cases.

610. Triangle Judgement
View on LeetCode

SELECT x, y, z, 
CASE WHEN x + y > z AND x + z > y AND y + z > x THEN 'Yes'
ELSE 'No' END AS triangle
FROM Triangle
This query determines whether three line segments can form a triangle using the triangle inequality theorem.

180. Consecutive Numbers
View on LeetCode

WITH cte AS (
  SELECT id, num, 
    LEAD(num) OVER (ORDER BY id) AS next, 
    LAG(num) OVER (ORDER BY id) AS prev
  FROM Logs
) 
SELECT DISTINCT(num) AS ConsecutiveNums
FROM cte
WHERE num = next AND num = prev
This query uses window functions to find numbers that appear at least three times consecutively in the logs.

1164. Product Price at a Given Date
View on LeetCode

SELECT product_id, new_price AS price
FROM products
WHERE (product_id, change_date) IN
(   
    SELECT product_id, MAX(change_date)
    FROM products
    WHERE change_date <= '2019-08-16'
    GROUP BY product_id
)
UNION

SELECT product_id, 10 AS price
FROM products
WHERE product_id NOT IN
(
  SELECT product_id
  FROM products
  WHERE change_date <= '2019-08-16'
)
This query finds the price of each product on '2019-08-16', using 10 as the default price if no price change occurred before that date.

1978. Employees Whose Manager Left the Company
View on LeetCode

SELECT employee_id
FROM Employees
WHERE manager_id NOT IN (
    SELECT employee_id 
    FROM Employees
)
AND salary < 30000
ORDER BY employee_id
This query finds employees with a salary less than 30000 whose manager is no longer with the company.

185. Department Top Three Salaries
View on LeetCode

WITH RankedSalaries AS 
(SELECT 
    e.Id AS employee_id,
    e.name AS employee,
    e.salary,
    e.departmentId,
    DENSE_RANK() OVER (PARTITION BY e.departmentId ORDER BY e.salary DESC) AS salary_rank 
FROM Employee e)
SELECT d.name AS Department,
r.employee,
r.salary
FROM Department d
JOIN RankedSalaries r ON r.departmentId = d.id
WHERE r.salary_rank <=3;
This query finds the top three highest paid employees in each department using the DENSE_RANK window function.

1667. Fix Names in a Table
View on LeetCode

SELECT user_id, CONCAT(UPPER(LEFT(name, 1)), LOWER(RIGHT(name, LENGTH(name)-1))) AS name
FROM Users
ORDER BY user_id
This query formats names to have the first letter capitalized and the rest in lowercase.

1527. Patients With a Condition
View on LeetCode

SELECT patient_id, patient_name, conditions 
FROM patients 
WHERE conditions LIKE '% DIAB1%' 
OR conditions LIKE 'DIAB1%'
This query finds patients who have Type I Diabetes, accounting for both cases where it's the first condition or a subsequent condition.

196. Delete Duplicate Emails
View on LeetCode

DELETE p
FROM Person p, Person q
WHERE p.id > q.id
AND q.Email = p.Email
This query deletes duplicate email entries, keeping only the one with the smallest ID.

176. Second Highest Salary
View on LeetCode

SELECT
(SELECT DISTINCT Salary 
FROM Employee
ORDER BY Salary DESC
LIMIT 1 OFFSET 1)
AS SecondHighestSalary
This query finds the second highest salary, returning NULL if there is no such salary. The subquery ensures NULL is returned instead of an empty result set.

1517. Find Users With Valid E-Mails
View on LeetCode

SELECT *
FROM Users
WHERE mail REGEXP '^[A-Za-z][A-Za-z0-9_\\.\\-]*@leetcode\\.com$'
This query uses a regular expression to find users with valid email addresses that match the specified pattern.

1204. Last Person to Fit in the Bus
View on LeetCode

WITH CTE AS (
    SELECT person_name, weight, turn, SUM(weight) 
    OVER(ORDER BY turn) AS total_weight
    FROM Queue
)
SELECT person_name
FROM cte
WHERE total_weight <=1000
ORDER BY total_weight DESC
LIMIT 1;
This query finds the last person who can fit on a bus with a weight limit of 1000 kg, using a window function to calculate cumulative weight.

1907. Count Salary Categories
View on LeetCode

SELECT 'Low Salary' AS category, SUM(IF(income<20000,1,0)) AS accounts_count 
FROM Accounts
UNION
SELECT 'Average Salary' AS category, SUM(IF(income>=20000 AND income<=50000,1,0)) AS accounts_count 
FROM Accounts
UNION
SELECT 'High Salary' AS category, SUM(IF(income>50000,1,0)) AS accounts_count 
FROM Accounts
This query counts accounts in three salary categories: Low (< 20000), Average (20000-50000), and High (> 50000).

626. Exchange Seats
View on LeetCode

SELECT id, 
CASE WHEN MOD(id,2)=0 THEN (LAG(student) OVER (ORDER BY id))
ELSE (LEAD(student, 1, student) OVER (ORDER BY id))
END AS 'Student'
FROM Seat
This query swaps the names of adjacent students without changing IDs, using window functions to handle the swapping logic.

1327. List the Products Ordered in a Period
View on LeetCode

SELECT p.product_name, SUM(o.unit) AS unit
FROM Products p
LEFT JOIN Orders o
ON p.product_id = o.product_id
WHERE DATE_FORMAT(order_date, '%Y-%m') = '2020-02'
GROUP BY p.product_name
HAVING SUM(o.unit) >= 100
This query lists products that had at least 100 units ordered in February 2020.

1484. Group Sold Products By The Date
View on LeetCode

SELECT sell_date, 
COUNT(DISTINCT product) AS num_sold,
GROUP_CONCAT(DISTINCT product) AS 'products' 
FROM Activities
GROUP BY sell_date
ORDER BY sell_date
This query uses GROUP_CONCAT to create a comma-separated list of products sold on each date, along with the count of unique products.

1341. Movie Rating
View on LeetCode

(SELECT name AS results
FROM Users u
LEFT JOIN MovieRating mr
ON u.user_id = mr.user_id
GROUP BY name
ORDER BY COUNT(rating) DESC, name ASC
LIMIT 1)

UNION ALL

(SELECT title
FROM Movies m
LEFT JOIN MovieRating mr
ON m.movie_id = mr.movie_id
WHERE DATE_FORMAT(created_at, '%Y-%m') = '2020-02'
GROUP BY title
ORDER BY AVG(rating) DESC, title ASC
LIMIT 1 
)
This query finds both the user who has rated the most movies and the movie with the highest average rating in February 2020.

1321. Restaurant Growth
View on LeetCode

SELECT visited_on, amount, ROUND(amount/7, 2) AS average_amount
FROM (
    SELECT DISTINCT visited_on,
    SUM(amount) OVER(ORDER BY visited_on RANGE BETWEEN INTERVAL 6 DAY PRECEDING AND CURRENT ROW) AS amount,
    MIN(visited_on) OVER() day_1
    FROM Customer
) t
WHERE visited_on >= day_1+6;
This query calculates a 7-day moving average of customer amounts, starting from the 7th day of available data.

602. Friend Requests II: Who Has the Most Friends
View on LeetCode

WITH CTE AS (
    SELECT requester_id AS id FROM RequestAccepted
    UNION ALL
    SELECT accepter_id AS id FROM RequestAccepted
)

SELECT id, COUNT(id) AS num
FROM CTE
GROUP BY id
ORDER BY num DESC
LIMIT 1
This query finds the user with the most friends by counting both requester and accepter occurrences in the RequestAccepted table.

585. Investments in 2016
View on LeetCode

SELECT
    ROUND(SUM(tiv_2016),2) AS tiv_2016
FROM insurance
WHERE tiv_2015 IN (SELECT tiv_2015 FROM insurance GROUP BY tiv_2015 HAVING COUNT(*) > 1)
AND (lat,lon) IN (SELECT lat,lon FROM insurance GROUP BY lat,lon HAVING COUNT(*) = 1)
This query finds the sum of insurance investments in 2016 for policies that have the same TIV_2015 as at least one other policy and a unique location.



