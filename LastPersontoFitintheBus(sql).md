~~~~mysql
# Write your MySQL query statement below
SELECT person_name 
FROM (SELECT person_name, turn, SUM(weight) OVER (ORDER BY turn)
    AS cumulative_turn FROM Queue) AS cum_table
WHERE cumulative_turn <= 1000
ORDER BY turn DESC
LIMIT 1
~~~~
