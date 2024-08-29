~~~~mysql
# Use left join to include the distance whether its null or not, 
# COALESCE for filtering the null
SELECT u.name, COALESCE(SUM(distance), 0) AS "travelled_distance"
FROM Users u
LEFT JOIN Rides r ON u.id = r.user_id
GROUP BY u.id
ORDER BY 2 DESC, 1 ASC
~~~~
