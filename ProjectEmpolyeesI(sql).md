~~~~mysql
# Write your MySQL query statement below
SELECT p.project_id, ROUND(AVG(e.experience_years),2) as average_years
FROM Project p
LEFT JOIN Employee e
USING (employee_id)
GROUP BY 1
~~~~
