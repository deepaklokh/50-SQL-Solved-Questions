<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LeetCode Top SQL 50 - Questions and Answers</title>
    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/prismjs@1.29.0/themes/prism.min.css">
    <style>
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
            line-height: 1.6;
            color: #333;
            background-color: #f8f9fa;
            padding: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }
        .question-container {
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            margin-bottom: 2rem;
            padding: 1.5rem;
        }
        .sql-solution {
            background-color: #f5f7f9;
            border-radius: 6px;
            padding: 1rem;
            margin: 1rem 0;
            overflow-x: auto;
        }
        pre {
            white-space: pre-wrap;
            word-wrap: break-word;
        }
        code {
            font-family: 'Courier New', Courier, monospace;
        }
        h1, h2, h3 {
            font-weight: 700;
        }
        .toc-link {
            display: block;
            padding: 0.25rem 0;
            text-decoration: none;
            color: #0366d6;
        }
        .toc-link:hover {
            text-decoration: underline;
        }
        .back-to-top {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background-color: #0366d6;
            color: white;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            box-shadow: 0 2px 5px rgba(0,0,0,0.2);
            transition: all 0.3s ease;
        }
        .back-to-top:hover {
            background-color: #0255b3;
            transform: translateY(-2px);
        }
        @media print {
            .back-to-top {
                display: none;
            }
        }
    </style>
</head>
<body class="bg-gray-50">
    <div class="container mx-auto px-4 py-8">
        <header class="mb-12 text-center">
            <h1 class="text-4xl font-bold mb-4">LeetCode Top SQL 50 - Questions and Answers</h1>
            <p class="text-lg text-gray-700 mb-8">A comprehensive collection of solutions for the <a href="https://leetcode.com/studyplan/top-sql-50/" class="text-blue-600 hover:underline" target="_blank">SQL 50 Study Plan</a> on LeetCode</p>
        </header>

        <div class="bg-white rounded-lg shadow-md p-6 mb-10">
            <h2 class="text-2xl font-bold mb-4">Table of Contents</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
                <div>
                    <a href="#q1757" class="toc-link">1757. Recyclable and Low Fat Products</a>
                    <a href="#q584" class="toc-link">584. Find Customer Referee</a>
                    <a href="#q595" class="toc-link">595. Big Countries</a>
                    <a href="#q1148" class="toc-link">1148. Article Views I</a>
                    <a href="#q1683" class="toc-link">1683. Invalid Tweets</a>
                    <a href="#q1378" class="toc-link">1378. Replace Employee ID With The Unique Identifier</a>
                    <a href="#q1068" class="toc-link">1068. Product Sales Analysis I</a>
                    <a href="#q1581" class="toc-link">1581. Customer Who Visited but Did Not Make Any Transactions</a>
                    <a href="#q197" class="toc-link">197. Rising Temperature</a>
                    <a href="#q1661" class="toc-link">1661. Average Time of Process per Machine</a>
                    <a href="#q577" class="toc-link">577. Employee Bonus</a>
                    <a href="#q1280" class="toc-link">1280. Students and Examinations</a>
                    <a href="#q570" class="toc-link">570. Managers with at Least 5 Direct Reports</a>
                    <a href="#q1934" class="toc-link">1934. Confirmation Rate</a>
                    <a href="#q620" class="toc-link">620. Not Boring Movies</a>
                    <a href="#q1251" class="toc-link">1251. Average Selling Price</a>
                    <a href="#q1075" class="toc-link">1075. Project Employees I</a>
                </div>
                <div>
                    <a href="#q1633" class="toc-link">1633. Percentage of Users Attended a Contest</a>
                    <a href="#q1211" class="toc-link">1211. Queries Quality and Percentage</a>
                    <a href="#q1193" class="toc-link">1193. Monthly Transactions I</a>
                    <a href="#q1174" class="toc-link">1174. Immediate Food Delivery II</a>
                    <a href="#q550" class="toc-link">550. Game Play Analysis IV</a>
                    <a href="#q2356" class="toc-link">2356. Number of Unique Subjects Taught by Each Teacher</a>
                    <a href="#q1141" class="toc-link">1141. User Activity for the Past 30 Days I</a>
                    <a href="#q1070" class="toc-link">1070. Product Sales Analysis III</a>
                    <a href="#q596" class="toc-link">596. Classes More Than 5 Students</a>
                    <a href="#q1729" class="toc-link">1729. Find Followers Count</a>
                    <a href="#q619" class="toc-link">619. Biggest Single Number</a>
                    <a href="#q1045" class="toc-link">1045. Customers Who Bought All Products</a>
                    <a href="#q1731" class="toc-link">1731. The Number of Employees Which Report to Each Employee</a>
                    <a href="#q1789" class="toc-link">1789. Primary Department for Each Employee</a>
                    <a href="#q610" class="toc-link">610. Triangle Judgement</a>
                    <a href="#q180" class="toc-link">180. Consecutive Numbers</a>
                </div>
                <div>
                    <a href="#q1164" class="toc-link">1164. Product Price at a Given Date</a>
                    <a href="#q1978" class="toc-link">1978. Employees Whose Manager Left the Company</a>
                    <a href="#q185" class="toc-link">185. Department Top Three Salaries</a>
                    <a href="#q1667" class="toc-link">1667. Fix Names in a Table</a>
                    <a href="#q1527" class="toc-link">1527. Patients With a Condition</a>
                    <a href="#q196" class="toc-link">196. Delete Duplicate Emails</a>
                    <a href="#q176" class="toc-link">176. Second Highest Salary</a>
                    <a href="#q1517" class="toc-link">1517. Find Users With Valid E-Mails</a>
                    <a href="#q1204" class="toc-link">1204. Last Person to Fit in the Bus</a>
                    <a href="#q1907" class="toc-link">1907. Count Salary Categories</a>
                    <a href="#q626" class="toc-link">626. Exchange Seats</a>
                    <a href="#q1327" class="toc-link">1327. List the Products Ordered in a Period</a>
                    <a href="#q1484" class="toc-link">1484. Group Sold Products By The Date</a>
                    <a href="#q1341" class="toc-link">1341. Movie Rating</a>
                    <a href="#q1321" class="toc-link">1321. Restaurant Growth</a>
                    <a href="#q602" class="toc-link">602. Friend Requests II: Who Has the Most Friends</a>
                    <a href="#q585" class="toc-link">585. Investments in 2016</a>
                </div>
            </div>
        </div>

        <!-- Questions and Solutions -->
        <div class="space-y-8">
            <!-- Question 1 -->
            <div id="q1757" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1757. Recyclable and Low Fat Products</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/recyclable-and-low-fat-products/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT product_id
FROM Products
WHERE low_fats = 'Y'
AND recyclable = 'Y'</code></pre>
                </div>
                <p class="text-gray-700">This query selects product IDs where both low_fats and recyclable values are 'Y'.</p>
            </div>

            <!-- Question 2 -->
            <div id="q584" class="question-container">
                <h2 class="text-2xl font-bold mb-2">584. Find Customer Referee</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/find-customer-referee" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT name 
FROM Customer 
WHERE referee_id != 2 OR referee_id IS null</code></pre>
                </div>
                <p class="text-gray-700">This query returns the names of customers who weren't referred by customer with id = 2 or weren't referred at all (NULL referee_id).</p>
            </div>

            <!-- Question 3 -->
            <div id="q595" class="question-container">
                <h2 class="text-2xl font-bold mb-2">595. Big Countries</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/big-countries/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT name, population, area
FROM WORLD
WHERE area >= 3000000
OR population >= 25000000</code></pre>
                </div>
                <p class="text-gray-700">This query selects countries that are considered "big" - either having an area of at least 3 million square km or a population of at least 25 million.</p>
            </div>

            <!-- Question 4 -->
            <div id="q1148" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1148. Article Views I</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/article-views-i" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT DISTINCT author_id as id
FROM Views
WHERE viewer_id >= 1
AND author_id = viewer_id
ORDER BY author_id</code></pre>
                </div>
                <p class="text-gray-700">This query finds the IDs of authors who have viewed their own articles. It returns distinct author IDs in ascending order.</p>
            </div>

            <!-- Question 5 -->
            <div id="q1683" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1683. Invalid Tweets</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/invalid-tweets/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT tweet_id
FROM Tweets
WHERE length(content) > 15</code></pre>
                </div>
                <p class="text-gray-700">This query finds tweet IDs where the content length exceeds 15 characters, which are considered invalid tweets.</p>
            </div>

            <!-- Question 6 -->
            <div id="q1378" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1378. Replace Employee ID With The Unique Identifier</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/replace-employee-id-with-the-unique-identifier" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT unique_id, name
FROM Employees e
LEFT JOIN EmployeeUNI eu
ON e.id = eu.id</code></pre>
                </div>
                <p class="text-gray-700">This query performs a LEFT JOIN to match employees with their unique identifiers, preserving all employee records even if they don't have a unique identifier.</p>
            </div>

            <!-- Question 7 -->
            <div id="q1068" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1068. Product Sales Analysis I</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/product-sales-analysis-i/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT product_name, year, price
FROM Sales s
LEFT JOIN Product p
ON s.product_id = p.product_id</code></pre>
                </div>
                <p class="text-gray-700">This query joins the Sales and Product tables to show product_name, year, and price for each sale.</p>
            </div>

            <!-- Question 8 -->
            <div id="q1581" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1581. Customer Who Visited but Did Not Make Any Transactions</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/customer-who-visited-but-did-not-make-any-transactions/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT customer_id, COUNT(*) as count_no_trans
FROM Visits 
WHERE visit_id NOT IN (SELECT DISTINCT visit_id FROM Transactions)
GROUP BY customer_id</code></pre>
                </div>
                <p class="text-gray-700">This query finds customers who visited but didn't make any transactions, counting the number of such visits for each customer.</p>
            </div>

            <!-- Question 9 -->
            <div id="q197" class="question-container">
                <h2 class="text-2xl font-bold mb-2">197. Rising Temperature</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/rising-temperature/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT w1.id 
FROM Weather w1, Weather w2
WHERE DATEDIFF(w1.recordDate, w2.recordDate) = 1
AND w1.temperature > w2.temperature</code></pre>
                </div>
                <p class="text-gray-700">Alternative solution:</p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT w1.id
FROM Weather w1, Weather w2
WHERE w1.temperature > w2.temperature
AND SUBDATE(w1.recordDate, 1) = w2.recordDate</code></pre>
                </div>
                <p class="text-gray-700">This query finds weather records where the temperature is higher than the previous day's temperature.</p>
            </div>

            <!-- Question 10 -->
            <div id="q1661" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1661. Average Time of Process per Machine</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/average-time-of-process-per-machine/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT machine_id, ROUND(AVG(end - start), 3) AS processing_time
FROM 
(SELECT machine_id, process_id, 
    MAX(CASE WHEN activity_type = 'start' THEN timestamp END) AS start,
    MAX(CASE WHEN activity_type = 'end' THEN timestamp END) AS end
 FROM Activity 
  GROUP BY machine_id, process_id) AS subq
GROUP BY machine_id</code></pre>
                </div>
                <p class="text-gray-700">This query calculates the average processing time for each machine by first grouping start and end timestamps for each process, then calculating the average time difference.</p>
            </div>

            <!-- Question 11 -->
            <div id="q577" class="question-container">
                <h2 class="text-2xl font-bold mb-2">577. Employee Bonus</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/employee-bonus/solutions/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT name, bonus
FROM Employee e
LEFT JOIN Bonus b
ON e.empId = b.empId
WHERE bonus < 1000
OR bonus IS NULL</code></pre>
                </div>
                <p class="text-gray-700">This query finds employees who received a bonus of less than 1000 or no bonus at all.</p>
            </div>

            <!-- Question 12 -->
            <div id="q1280" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1280. Students and Examinations</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/students-and-examinations/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT a.student_id, a.student_name, b.subject_name, COUNT(c.subject_name) AS attended_exams
FROM Students a
JOIN Subjects b
LEFT JOIN Examinations c
ON a.student_id = c.student_id
AND b.subject_name = c.subject_name
GROUP BY 1, 3
ORDER BY 1, 3</code></pre>
                </div>
                <p class="text-gray-700">This query generates a report showing the number of times each student attended each exam, including zero counts for subjects they didn't attend.</p>
            </div>

            <!-- Question 13 -->
            <div id="q570" class="question-container">
                <h2 class="text-2xl font-bold mb-2">570. Managers with at Least 5 Direct Reports</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/managers-with-at-least-5-direct-reports" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT name 
FROM Employee 
WHERE id IN
  (SELECT managerId 
   FROM Employee 
   GROUP BY managerId 
   HAVING COUNT(*) >= 5
  )</code></pre>
                </div>
                <p class="text-gray-700">Alternative solution:</p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT a.name
FROM Employee a
JOIN Employee b
WHERE a.id = b.managerId
GROUP BY b.managerId
HAVING COUNT(*) >= 5</code></pre>
                </div>
                <p class="text-gray-700">This query finds managers who have at least 5 direct reports.</p>
            </div>

            <!-- Question 14 -->
            <div id="q1934" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1934. Confirmation Rate</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/confirmation-rate/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT 
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
GROUP BY s.user_id;</code></pre>
                </div>
                <p class="text-gray-700">This query calculates the confirmation rate for each user, which is the number of 'confirmed' actions divided by the total number of confirmation requests.</p>
            </div>

            <!-- Question 15 -->
            <div id="q620" class="question-container">
                <h2 class="text-2xl font-bold mb-2">620. Not Boring Movies</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/not-boring-movies" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT *
FROM Cinema
WHERE id % 2 <> 0 
AND description <> "boring"
ORDER BY rating DESC</code></pre>
                </div>
                <p class="text-gray-700">This query selects movies with odd IDs and a non-boring description, sorted by rating in descending order.</p>
            </div>

            <!-- Question 16 -->
            <div id="q1251" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1251. Average Selling Price</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/average-selling-price/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT p.product_id, 
  ROUND(SUM(price * units) / SUM(units), 2) AS average_price
FROM Prices p
LEFT JOIN UnitsSold s
ON p.product_id = s.product_id
AND purchase_date BETWEEN start_date AND end_date
GROUP BY p.product_id</code></pre>
                </div>
                <p class="text-gray-700">This query calculates the average selling price for each product, considering only sales that occurred during valid price periods.</p>
            </div>

            <!-- Question 17 -->
            <div id="q1075" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1075. Project Employees I</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/project-employees-i" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT project_id, ROUND(AVG(experience_years), 2) average_years
FROM Project p 
LEFT JOIN Employee e
ON p.employee_id = e.employee_id
GROUP BY project_id</code></pre>
                </div>
                <p class="text-gray-700">This query calculates the average years of experience for employees working on each project.</p>
            </div>

            <!-- Question 18 -->
            <div id="q1633" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1633. Percentage of Users Attended a Contest</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/percentage-of-users-attended-a-contest" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT r.contest_id,
       ROUND(COUNT(DISTINCT r.user_id) * 100 / (SELECT COUNT(DISTINCT user_id) FROM Users), 2) AS percentage
FROM Register r
GROUP BY r.contest_id
ORDER BY percentage DESC, r.contest_id ASC;</code></pre>
                </div>
                <p class="text-gray-700">This query calculates the percentage of users who registered for each contest, ordering results by percentage (descending) and contest ID (ascending).</p>
            </div>

            <!-- Question 19 -->
            <div id="q1211" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1211. Queries Quality and Percentage</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/queries-quality-and-percentage" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT query_name, 
    ROUND(AVG(rating/position), 2) AS quality, 
    ROUND(SUM(IF(rating < 3, 1, 0)) * 100/ COUNT(rating), 2) AS poor_query_percentage
FROM Queries
GROUP BY query_name</code></pre>
                </div>
                <p class="text-gray-700">Alternative solution:</p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT query_name, 
    ROUND(AVG(rating/position), 2) AS quality, 
    ROUND(SUM(
        CASE WHEN rating < 3 THEN 1 ELSE 0 END
    ) * 100/ COUNT(rating), 2) AS poor_query_percentage
FROM Queries
GROUP BY query_name</code></pre>
                </div>
                <p class="text-gray-700">This query calculates query quality metrics: the quality (avg of rating/position) and the percentage of poor queries (rating < 3).</p>
            </div>

            <!-- Question 20 -->
            <div id="q1193" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1193. Monthly Transactions I</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/monthly-transactions-i/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT DATE_FORMAT(trans_date, '%Y-%m') month, country, 
        COUNT(state) trans_count, 
        SUM(IF(state = 'approved', 1, 0)) approved_count, 
        SUM(amount) trans_total_amount,
        SUM(IF(state = 'approved', amount, 0)) approved_total_amount
FROM Transactions
GROUP BY 1, 2</code></pre>
                </div>
                <p class="text-gray-700">Alternative solution:</p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT DATE_FORMAT(trans_date, '%Y-%m') month, country, 
        COUNT(state) trans_count, 
        SUM(CASE WHEN state = 'approved' THEN 1 ELSE 0 END) approved_count, 
        SUM(amount) trans_total_amount,
        SUM(CASE WHEN state = 'approved' THEN amount ELSE 0 END) approved_total_amount
FROM Transactions
GROUP BY 1, 2</code></pre>
                </div>
                <p class="text-gray-700">This query summarizes transaction data by month and country, including counts and amounts for both total and approved transactions.</p>
            </div>

            <!-- Question 21 -->
            <div id="q1174" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1174. Immediate Food Delivery II</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/immediate-food-delivery-ii/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT
    ROUND((COUNT(CASE WHEN d.order_date = d.customer_pref_delivery_date THEN 1 END) / COUNT(*)) * 100, 2)  immediate_percentage
FROM Delivery d
WHERE d.order_date = (
    SELECT
    MIN(order_date)
    FROM Delivery
    WHERE customer_id = d.customer_id
    );</code></pre>
                </div>
                <p class="text-gray-700">Alternative solution:</p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT ROUND(AVG(temp.order_date=temp.customer_pref_delivery_date) * 100, 2) immediate_percentage
FROM (
    SELECT *, RANK() OVER(partition by customer_id ORDER BY order_date) od
    FROM Delivery) temp
WHERE temp.od = 1</code></pre>
                </div>
                <p class="text-gray-700">This query calculates the percentage of first-time orders that were immediate (where preferred delivery date equals order date).</p>
            </div>

            <!-- Question 22 -->
            <div id="q550" class="question-container">
                <h2 class="text-2xl font-bold mb-2">550. Game Play Analysis IV</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/game-play-analysis-iv/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">WITH login_date AS (SELECT player_id, MIN(event_date) AS first_login
FROM Activity
GROUP BY player_id),

recent_login AS (
SELECT *, DATE_ADD(first_login, INTERVAL 1 DAY) AS next_day
FROM login_date)

SELECT ROUND((SELECT COUNT(DISTINCT(player_id))
FROM Activity
WHERE (player_id, event_date) IN 
(SELECT player_id, next_day FROM recent_login)) / (SELECT COUNT(DISTINCT player_id) FROM Activity), 2) AS fraction</code></pre>
                </div>
                <p class="text-gray-700">This query finds the fraction of players who logged in again on the day after their first login.</p>
            </div>

            <!-- Question 23 -->
            <div id="q2356" class="question-container">
                <h2 class="text-2xl font-bold mb-2">2356. Number of Unique Subjects Taught by Each Teacher</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/number-of-unique-subjects-taught-by-each-teacher" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT teacher_id, COUNT(DISTINCT subject_id) cnt
FROM Teacher
GROUP BY teacher_id</code></pre>
                </div>
                <p class="text-gray-700">This query counts the number of unique subjects taught by each teacher.</p>
            </div>

            <!-- Question 24 -->
            <div id="q1141" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1141. User Activity for the Past 30 Days I</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/user-activity-for-the-past-30-days-i/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT activity_date as day, COUNT(DISTINCT user_id) AS active_users
FROM Activity
WHERE activity_date BETWEEN DATE_SUB('2019-07-27', INTERVAL 29 DAY) AND '2019-07-27'
GROUP BY activity_date</code></pre>
                </div>
                <p class="text-gray-700">This query counts the number of active users for each day within a 30-day period ending on '2019-07-27'.</p>
            </div>

            <!-- Question 25 -->
            <div id="q1070" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1070. Product Sales Analysis III</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/product-sales-analysis-iii/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT s.product_id, s.year AS first_year, s.quantity, s.price
FROM Sales s
JOIN (
  SELECT product_id, MIN(year) AS year 
  FROM sales 
  GROUP BY product_id
  ) p
ON s.product_id = p.product_id
AND s.year = p.year</code></pre>
                </div>
                <p class="text-gray-700">Alternative solution:</p>
                <div class="sql-solution">
                    <pre><code class="language-sql">WITH first_year_sales AS (
  SELECT s.product_id, MIN(s.year) as first_year
  FROM Sales s
  INNER JOIN Product p
  ON s.product_id = p.product_id
  GROUP BY s.product_id)
SELECT f.product_id, f.first_year, s.quantity, s.price
FROM first_year_sales f
JOIN Sales s 
ON f.product_id = s.product_id
AND f.first_year = s.year</code></pre>
                </div>
                <p class="text-gray-700">This query finds the first year of sales for each product and returns the quantity and price from that year.</p>
            </div>

            <!-- Question 26 -->
            <div id="q596" class="question-container">
                <h2 class="text-2xl font-bold mb-2">596. Classes More Than 5 Students</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/classes-more-than-5-students/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT class
FROM Courses
GROUP BY class
HAVING COUNT(student) >= 5</code></pre>
                </div>
                <p class="text-gray-700">This query finds classes that have at least 5 students.</p>
            </div>

            <!-- Question 27 -->
            <div id="q1729" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1729. Find Followers Count</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/find-followers-count/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT user_id, COUNT(DISTINCT follower_id) AS followers_count
FROM Followers
GROUP BY user_id
ORDER BY user_id ASC</code></pre>
                </div>
                <p class="text-gray-700">This query counts the number of followers for each user and orders the results by user_id.</p>
            </div>

            <!-- Question 28 -->
            <div id="q619" class="question-container">
                <h2 class="text-2xl font-bold mb-2">619. Biggest Single Number</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/biggest-single-number/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT COALESCE(
  (SELECT num
  FROM MyNumbers
  GROUP BY num
  HAVING COUNT(num) = 1
  ORDER BY num DESC
  LIMIT 1), null) 
  AS num</code></pre>
                </div>
                <p class="text-gray-700">This query finds the largest number that appears only once in the table, returning null if there is no such number.</p>
            </div>

            <!-- Question 29 -->
            <div id="q1045" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1045. Customers Who Bought All Products</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/customers-who-bought-all-products/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT customer_id
FROM Customer
GROUP BY customer_id
HAVING COUNT(DISTINCT product_key) = (
  SELECT COUNT(product_key)
  FROM Product
)</code></pre>
                </div>
                <p class="text-gray-700">This query finds customers who have purchased every product available in the Product table.</p>
            </div>

            <!-- Question 30 -->
            <div id="q1731" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1731. The Number of Employees Which Report to Each Employee</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/the-number-of-employees-which-report-to-each-employee/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT e1.employee_id, e1.name, COUNT(e2.employee_id) reports_count, ROUND(AVG(e2.age)) average_age 
FROM Employees e1, Employees e2
WHERE e1.employee_id = e2.reports_to
GROUP BY e1.employee_id
HAVING reports_count > 0
ORDER BY e1.employee_id</code></pre>
                </div>
                <p class="text-gray-700">This query finds managers, counts their direct reports, and calculates the average age of those reports.</p>
            </div>

            <!-- Question 31 -->
            <div id="q1789" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1789. Primary Department for Each Employee</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/primary-department-for-each-employee/?envType=study-plan-v2&envId=top-sql-50" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT employee_id, department_id
FROM Employee 
WHERE primary_flag = 'Y'
UNION
SELECT employee_id, department_id
FROM Employee
GROUP BY employee_id
HAVING COUNT(employee_id)=1</code></pre>
                </div>
                <p class="text-gray-700">Alternative solution:</p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT employee_id,department_id
FROM Employee
WHERE primary_flag = 'Y' OR employee_id IN
    (SELECT employee_id
     FROM employee
     GROUP BY employee_id
     HAVING COUNT(department_id) = 1
    )</code></pre>
                </div>
                <p class="text-gray-700">This query identifies the primary department for each employee, considering both primary_flag and single-department cases.</p>
            </div>

            <!-- Question 32 -->
            <div id="q610" class="question-container">
                <h2 class="text-2xl font-bold mb-2">610. Triangle Judgement</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/triangle-judgement/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT x, y, z, 
CASE WHEN x + y > z AND x + z > y AND y + z > x THEN 'Yes'
ELSE 'No' END AS triangle
FROM Triangle</code></pre>
                </div>
                <p class="text-gray-700">This query determines whether three line segments can form a triangle using the triangle inequality theorem.</p>
            </div>

            <!-- Question 33 -->
            <div id="q180" class="question-container">
                <h2 class="text-2xl font-bold mb-2">180. Consecutive Numbers</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/consecutive-numbers/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">WITH cte AS (
  SELECT id, num, 
    LEAD(num) OVER (ORDER BY id) AS next, 
    LAG(num) OVER (ORDER BY id) AS prev
  FROM Logs
) 
SELECT DISTINCT(num) AS ConsecutiveNums
FROM cte
WHERE num = next AND num = prev</code></pre>
                </div>
                <p class="text-gray-700">This query uses window functions to find numbers that appear at least three times consecutively in the logs.</p>
            </div>

            <!-- Question 34 -->
            <div id="q1164" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1164. Product Price at a Given Date</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/product-price-at-a-given-date" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT product_id, new_price AS price
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
)</code></pre>
                </div>
                <p class="text-gray-700">This query finds the price of each product on '2019-08-16', using 10 as the default price if no price change occurred before that date.</p>
            </div>

            <!-- Question 35 -->
            <div id="q1978" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1978. Employees Whose Manager Left the Company</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/employees-whose-manager-left-the-company" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT employee_id
FROM Employees
WHERE manager_id NOT IN (
    SELECT employee_id 
    FROM Employees
)
AND salary < 30000
ORDER BY employee_id</code></pre>
                </div>
                <p class="text-gray-700">This query finds employees with a salary less than 30000 whose manager is no longer with the company.</p>
            </div>

            <!-- Question 36 -->
            <div id="q185" class="question-container">
                <h2 class="text-2xl font-bold mb-2">185. Department Top Three Salaries</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/department-top-three-salaries" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">WITH RankedSalaries AS 
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
WHERE r.salary_rank <=3;</code></pre>
                </div>
                <p class="text-gray-700">This query finds the top three highest paid employees in each department using the DENSE_RANK window function.</p>
            </div>

            <!-- Question 37 -->
            <div id="q1667" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1667. Fix Names in a Table</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/fix-names-in-a-table" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT user_id, CONCAT(UPPER(LEFT(name, 1)), LOWER(RIGHT(name, LENGTH(name)-1))) AS name
FROM Users
ORDER BY user_id</code></pre>
                </div>
                <p class="text-gray-700">This query formats names to have the first letter capitalized and the rest in lowercase.</p>
            </div>

            <!-- Question 38 -->
            <div id="q1527" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1527. Patients With a Condition</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/patients-with-a-condition" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT patient_id, patient_name, conditions 
FROM patients 
WHERE conditions LIKE '% DIAB1%' 
OR conditions LIKE 'DIAB1%'</code></pre>
                </div>
                <p class="text-gray-700">This query finds patients who have Type I Diabetes, accounting for both cases where it's the first condition or a subsequent condition.</p>
            </div>

            <!-- Question 39 -->
            <div id="q196" class="question-container">
                <h2 class="text-2xl font-bold mb-2">196. Delete Duplicate Emails</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/delete-duplicate-emails" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">DELETE p
FROM Person p, Person q
WHERE p.id > q.id
AND q.Email = p.Email</code></pre>
                </div>
                <p class="text-gray-700">This query deletes duplicate email entries, keeping only the one with the smallest ID.</p>
            </div>

            <!-- Question 40 -->
            <div id="q176" class="question-container">
                <h2 class="text-2xl font-bold mb-2">176. Second Highest Salary</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/second-highest-salary" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT
(SELECT DISTINCT Salary 
FROM Employee
ORDER BY Salary DESC
LIMIT 1 OFFSET 1)
AS SecondHighestSalary</code></pre>
                </div>
                <p class="text-gray-700">This query finds the second highest salary, returning NULL if there is no such salary. The subquery ensures NULL is returned instead of an empty result set.</p>
            </div>

            <!-- Question 41 -->
            <div id="q1517" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1517. Find Users With Valid E-Mails</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/find-users-with-valid-e-mails" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT *
FROM Users
WHERE mail REGEXP '^[A-Za-z][A-Za-z0-9_\\.\\-]*@leetcode\\.com$'</code></pre>
                </div>
                <p class="text-gray-700">This query uses a regular expression to find users with valid email addresses that match the specified pattern.</p>
            </div>

            <!-- Question 42 -->
            <div id="q1204" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1204. Last Person to Fit in the Bus</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/last-person-to-fit-in-the-bus/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">WITH CTE AS (
    SELECT person_name, weight, turn, SUM(weight) 
    OVER(ORDER BY turn) AS total_weight
    FROM Queue
)
SELECT person_name
FROM cte
WHERE total_weight <=1000
ORDER BY total_weight DESC
LIMIT 1;</code></pre>
                </div>
                <p class="text-gray-700">This query finds the last person who can fit on a bus with a weight limit of 1000 kg, using a window function to calculate cumulative weight.</p>
            </div>

            <!-- Question 43 -->
            <div id="q1907" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1907. Count Salary Categories</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/count-salary-categories/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT 'Low Salary' AS category, SUM(IF(income<20000,1,0)) AS accounts_count 
FROM Accounts
UNION
SELECT 'Average Salary' AS category, SUM(IF(income>=20000 AND income<=50000,1,0)) AS accounts_count 
FROM Accounts
UNION
SELECT 'High Salary' AS category, SUM(IF(income>50000,1,0)) AS accounts_count 
FROM Accounts</code></pre>
                </div>
                <p class="text-gray-700">This query counts accounts in three salary categories: Low (< 20000), Average (20000-50000), and High (> 50000).</p>
            </div>

            <!-- Question 44 -->
            <div id="q626" class="question-container">
                <h2 class="text-2xl font-bold mb-2">626. Exchange Seats</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/exchange-seats/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT id, 
CASE WHEN MOD(id,2)=0 THEN (LAG(student) OVER (ORDER BY id))
ELSE (LEAD(student, 1, student) OVER (ORDER BY id))
END AS 'Student'
FROM Seat</code></pre>
                </div>
                <p class="text-gray-700">This query swaps the names of adjacent students without changing IDs, using window functions to handle the swapping logic.</p>
            </div>

            <!-- Question 45 -->
            <div id="q1327" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1327. List the Products Ordered in a Period</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/list-the-products-ordered-in-a-period/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT p.product_name, SUM(o.unit) AS unit
FROM Products p
LEFT JOIN Orders o
ON p.product_id = o.product_id
WHERE DATE_FORMAT(order_date, '%Y-%m') = '2020-02'
GROUP BY p.product_name
HAVING SUM(o.unit) >= 100</code></pre>
                </div>
                <p class="text-gray-700">This query lists products that had at least 100 units ordered in February 2020.</p>
            </div>

            <!-- Question 46 -->
            <div id="q1484" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1484. Group Sold Products By The Date</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/group-sold-products-by-the-date/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT sell_date, 
COUNT(DISTINCT product) AS num_sold,
GROUP_CONCAT(DISTINCT product) AS 'products' 
FROM Activities
GROUP BY sell_date
ORDER BY sell_date</code></pre>
                </div>
                <p class="text-gray-700">This query uses GROUP_CONCAT to create a comma-separated list of products sold on each date, along with the count of unique products.</p>
            </div>

            <!-- Question 47 -->
            <div id="q1341" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1341. Movie Rating</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/movie-rating/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">(SELECT name AS results
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
)</code></pre>
                </div>
                <p class="text-gray-700">This query finds both the user who has rated the most movies and the movie with the highest average rating in February 2020.</p>
            </div>

            <!-- Question 48 -->
            <div id="q1321" class="question-container">
                <h2 class="text-2xl font-bold mb-2">1321. Restaurant Growth</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/restaurant-growth/" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT visited_on, amount, ROUND(amount/7, 2) AS average_amount
FROM (
    SELECT DISTINCT visited_on,
    SUM(amount) OVER(ORDER BY visited_on RANGE BETWEEN INTERVAL 6 DAY PRECEDING AND CURRENT ROW) AS amount,
    MIN(visited_on) OVER() day_1
    FROM Customer
) t
WHERE visited_on >= day_1+6;</code></pre>
                </div>
                <p class="text-gray-700">This query calculates a 7-day moving average of customer amounts, starting from the 7th day of available data.</p>
            </div>

            <!-- Question 49 -->
            <div id="q602" class="question-container">
                <h2 class="text-2xl font-bold mb-2">602. Friend Requests II: Who Has the Most Friends</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/friend-requests-ii-who-has-the-most-friends" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">WITH CTE AS (
    SELECT requester_id AS id FROM RequestAccepted
    UNION ALL
    SELECT accepter_id AS id FROM RequestAccepted
)

SELECT id, COUNT(id) AS num
FROM CTE
GROUP BY id
ORDER BY num DESC
LIMIT 1</code></pre>
                </div>
                <p class="text-gray-700">This query finds the user with the most friends by counting both requester and accepter occurrences in the RequestAccepted table.</p>
            </div>

            <!-- Question 50 -->
            <div id="q585" class="question-container">
                <h2 class="text-2xl font-bold mb-2">585. Investments in 2016</h2>
                <p class="mb-4"><a href="https://leetcode.com/problems/investments-in-2016" class="text-blue-600 hover:underline" target="_blank">View on LeetCode</a></p>
                <div class="sql-solution">
                    <pre><code class="language-sql">SELECT
    ROUND(SUM(tiv_2016),2) AS tiv_2016
FROM insurance
WHERE tiv_2015 IN (SELECT tiv_2015 FROM insurance GROUP BY tiv_2015 HAVING COUNT(*) > 1)
AND (lat,lon) IN (SELECT lat,lon FROM insurance GROUP BY lat,lon HAVING COUNT(*) = 1)</code></pre>
                </div>
                <p class="text-gray-700">This query finds the sum of insurance investments in 2016 for policies that have the same TIV_2015 as at least one other policy and a unique location.</p>
            </div>
        </div>

        <footer class="mt-16 text-center text-gray-600">
            <p>These solutions are intended for educational purposes. If you find them helpful, please consider giving the GitHub repository a star!</p>
        </footer>
    </div>

    <a href="#" class="back-to-top">↑</a>

    <script src="https://cdn.jsdelivr.net/npm/prismjs@1.29.0/prism.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/prismjs@1.29.0/components/prism-sql.min.js"></script>
    <script>
        // Back to top functionality
        document.querySelector('.back-to-top').addEventListener('click', function(e) {
            e.preventDefault();
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        });

        // Show/hide back to top button based on scroll position
        window.addEventListener('scroll', function() {
            var backToTop = document.querySelector('.back-to-top');
            if (window.pageYOffset > 300) {
                backToTop.style.display = 'flex';
            } else {
                backToTop.style.display = 'none';
            }
        });
    </script>
</body>
</html>
