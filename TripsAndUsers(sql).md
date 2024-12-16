~~~mysql
# Write your MySQL query statement below
SELECT 
    t.request_at AS Day, 
    ROUND(
        SUM(CASE WHEN t.status != 'completed' THEN 1 ELSE 0 END) / 
        COUNT(DISTINCT t.id), 2
    ) AS "Cancellation Rate"
FROM Trips t
JOIN Users c ON t.Client_Id = c.Users_Id AND c.Banned = 'No'
JOIN Users d ON t.Driver_Id = d.Users_Id AND d.Banned = 'No'
WHERE t.Request_at BETWEEN '2013-10-01' AND '2013-10-03'
GROUP BY 1;
