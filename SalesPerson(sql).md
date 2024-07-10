~~~~mysql
# Write your MySQL query statement below
SELECT s.name 
FROM SalesPerson s
LEFT JOIN Orders o ON s.sales_id = o.sales_id
LEFT JOIN Company c ON c.com_id = o.com_id
GROUP BY s.sales_id
HAVING SUM(c.name = "RED") = 0 OR SUM(c.name IS NULL) > 0
~~~~
