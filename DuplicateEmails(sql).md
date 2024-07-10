# Write your MySQL query statement below
Select email as Email 
FROM Person
GROUP BY 1
HAVING COUNT(email) > 1
