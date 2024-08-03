~~~~mysql
# Write your MySQL query statement below
WITH CTE AS (
    SELECT requester_id as id
    FROM RequestAccepted

    UNION ALL

    SELECT accepter_id as id
    FROM RequestAccepted

)

SELECT id, COUNT(*) as num 
FROM CTE
GROUP BY id
ORDER BY 2 DESC
LIMIT 1
~~~~
