~~~~mysql
# Write your MySQL query statement below
SELECT c1.id, c1.movie, c1.description, c1.rating
FROM Cinema c1
WHERE c1.id % 2 = 1 AND c1.description != 'boring'
ORDER BY c1.rating DESC;
~~~~
