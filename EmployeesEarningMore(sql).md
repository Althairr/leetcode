Write a solution to find the employees who earn more than their managers

~~~~sql
  # Write your MySQL query statement below
  SELECT e1.name as "Employee" FROM Employee e1
  LEFT JOIN Employee e2 
  ON e1.ManagerId = e2.Id 
  WHERE e1.salary > e2.salary 
~~~~
