~~~~mysql
# Write your MySQL query statement below
SELECT r.contest_id, 
ROUND((COUNT(r.contest_id) / (SELECT COUNT(user_id) FROM Users) * 100),2) as percentage
FROM Register r 
LEFT JOIN Users u 
USING (user_id)
GROUP BY 1
ORDER BY 2 DESC, 1 ASC
~~~~
