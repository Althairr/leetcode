~~~~mysql
-- First, product that the price doesn't change before or in '2019-08-16'
SELECT
    product_id,
    10 AS price
FROM 
    products
GROUP BY
    product_id
HAVING
    MIN(change_date) > '2019-08-16'

UNION

-- Next, product with the changed price before or in '2019-08-16'
SELECT 
    p.product_id, 
    p.new_price
FROM 
    Products p
WHERE 
    (p.product_id, p.change_date) IN (
        SELECT 
            product_id, 
            MAX(change_date) AS recent_date
        FROM 
            Products
        WHERE 
            change_date <= '2019-08-16'
        GROUP BY 
            product_id
    );
~~~~
