~~~~mysql
# Write your MySQL query statement below
WITH CTE AS (
    SELECT d.name AS Department, e.name AS Employee, e.salary as Salary,
        dense_rank() over (partition by d.name order by e.salary desc) as Ranking
    FROM Employee e
    LEFT JOIN Department d 
    ON e.departmentId = d.id

)

SELECT Department, Employee, Salary 
FROM CTE
WHERE Ranking BETWEEN 1 AND 3
~~~~
