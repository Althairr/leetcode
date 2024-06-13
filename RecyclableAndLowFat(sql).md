~~~~mysql
# Write your MySQL query statement below
SELECT p1.product_id 
FROM Products p1
LEFT JOIN Products p2
ON p1.product_id = p2.product_id 
WHERE p2.low_fats = 'Y' AND p2.recyclable = 'Y';
~~~~
