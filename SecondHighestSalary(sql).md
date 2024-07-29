~~~~mysql
# We use subquery so that if there is not any answer given, the subquery will outputs 'null' forcefully
SELECT
  (SELECT DISTINCT Salary 
   FROM Employee 
   ORDER BY salary DESC 
   LIMIT 1 OFFSET 1) 
AS SecondHighestSalary;
~~~~
