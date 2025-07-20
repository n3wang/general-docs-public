---
tags:
  - software-engineer
  - sql
---
:t 
- This set of problems are leetcode sql based, with the objectives of sharping your sql skills before an intervew

## 118. Pascal's Triangle
:l [118. Pascal's Triangle](https://leetcode.com/problems/pascals-triangle/)
:t Array, Dynamic Programming

Write a solution to find all dates' `id` with higher temperatures compared to its previous dates
```sql
+---------------+---------+
| Column Name   | Type    |
+---------------+---------+
| id            | int     |
| recordDate    | date    |
| temperature   | int     |
+---------------+---------+
id is the column with unique values for this table.
There are no different rows with the same recordDate.
This table contains information about the temperature on a certain day.
```
https://leetcode.com/problems/rising-temperature/?envType=study-plan-v2&envId=top-sql-50

### Solution

```sql
SELECT id FROM (
    SELECT id, b - a as difference FROM
        (
            SELECT * 
            FROM 
                (SELECT recordDate + 1 AS recordDate, temperature AS b FROM weather) AS t1 
            INNER JOIN 
                (SELECT id, recordDate, temperature AS a FROM weather) AS t2 
            ON t1.recordDate = t2.recordDate
    )
) WHERE difference < 0;

```




Write a solution to find the IDs of the users who visited without making any transactions and the number of times they made these types of visits.
Return the result table sorted in any order.
```sql
Table: Visits

+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| visit_id    | int     |
| customer_id | int     |
+-------------+---------+
visit_id is the column with unique values for this table.
This table contains information about the customers who visited the mall.
 

Table: Transactions

+----------------+---------+
| Column Name    | Type    |
+----------------+---------+
| transaction_id | int     |
| visit_id       | int     |
| amount         | int     |
+----------------+---------+
transaction_id is column with unique values for this table.
This table contains information about the transactions made during the visit_id.
```
https://leetcode.com/problems/customer-who-visited-but-did-not-make-any-transactions/description/?envType=study-plan-v2&envId=top-sql-50
?x
```sql
SELECT customer_id, COUNT(*) AS count_no_trans
 FROM Visits WHERE visit_id NOT IN 
(SELECT DISTINCT visit_id FROM Transactions)
GROUP BY customer_id;
```




Write a solution to show the unique ID of each user, If a user does not have a unique ID replace just show null.
Return the result table in any order.
The result format is in the following example.
```sql
Table: `Employees`

+---------------+---------+
| Column Name   | Type    |
+---------------+---------+
| id            | int     |
| name          | varchar |
+---------------+---------+
id is the primary key (column with unique values) for this table.
Each row of this table contains the id and the name of an employee in a company.

Table: `EmployeeUNI`

+---------------+---------+
| Column Name   | Type    |
+---------------+---------+
| id            | int     |
| unique_id     | int     |
+---------------+---------+
(id, unique_id) is the primary key (combination of columns with unique values) for this table.
Each row of this table contains the id and the corresponding unique id of an employee in the company.
```
?x
```sql
SELECT unique_id, name FROM (
    (SELECT * FROM Employees) as e1 LEFT JOIN (SELECT * FROM EmployeeUNI) AS u1 ON e1.id=u1.id
)
```



x
```sql
x
```
hx
?x
```sql
x
```



x
```sql
x
```
hx
?x
```sql
x
```

