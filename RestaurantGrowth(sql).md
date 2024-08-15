~~~~mysql
# Write your MySQL query statement below
-- select the distinct date
SELECT distinct visited_on, 
        -- SUM the amount of the window 
        SUM(amount) OVER w AS "amount",
        -- calculate the 7-day rolling average, rounded to 2 decimal places
        ROUND((SUM(amount) OVER w)/7, 2) AS "average_amount"
FROM Customer

WINDOW w AS (
    -- order the data by visited_on
    ORDER BY visited_on

    -- define the window range: from 6 days before to the current row
    RANGE BETWEEN INTERVAL 6 DAY PRECEDING AND CURRENT ROW
)
-- skip the first 6 rows and fetch up to 9999 rows starting from the 7th row
LIMIT 6, 9999
~~~~
