~~~~mysql
# Write your MySQL query statement below
SELECT p.product_id, p.product_name
FROM Product p
LEFT JOIN Sales s
USING (product_id)
GROUP BY 1
HAVING MIN(s.sale_date) >= '2019-01-01' and MAX(sale_date) <= '2019-03-31'
~~~~
