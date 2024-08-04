~~~~mysql
# Write your MySQL query statement below
SELECT p.product_name, SUM(o.unit) AS unit
FROM Products p
LEFT JOIN Orders o 
USING (product_id)
#WHERE MONTH(o.order_date) = 2 AND YEAR(o.order_date) = 2020 
WHERE o.order_date BETWEEN "2020-02-01" AND "2020-02-29"
GROUP BY 1
HAVING unit >= 100
~~~~
