~~~~mysql
# Write your MySQL query statement below
SELECT 
    stock_name, 
    SUM(
        -- When buy, our capital gain will deficit
        CASE 
            WHEN operation = 'Buy' THEN -price
            WHEN operation = 'Sell' THEN price
        END 
    ) AS capital_gain_loss
FROM Stocks
GROUP BY 1
