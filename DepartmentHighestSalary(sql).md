~~~~mysql
# Write your MySQL query statement 
SELECT d.name AS Department, e.name AS Employee, e.salary
FROM Employee e
JOIN Department d ON e.departmentId = d.id
WHERE (e.departmentId, salary) IN 
    (
        SELECT 
            departmentId, 
            MAX(Salary) 
        FROM 
            Employee 
        GROUP BY 
            departmentId
    )
