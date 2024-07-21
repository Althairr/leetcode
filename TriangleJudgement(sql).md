~~~~mysql
# Write your MySQL query statement below
# we can explicitly called all the columns (e.g: "x,y,z"). But,
# the runtime will be faster if we just use wildcard "*"
SELECT *, IF(x + y > z AND x + z > y AND y + z > x, "Yes", "No") AS triangle
FROM Triangle
~~~~
