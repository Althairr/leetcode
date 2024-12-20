~~~~mysql
# Write your MySQL query statement below
WITH FilteredStadium AS (
    SELECT *, id - ROW_NUMBER() OVER (ORDER BY id ASC) AS GroupID
    FROM Stadium    
    WHERE people >= 100
),
GroupedStadium AS (
    SELECT *, COUNT(GroupID) OVER (PARTITION BY GroupID) AS GroupSize
    FROM FilteredStadium
)

SELECT id, visit_date, people
FROM GroupedStadium 
WHERE GroupSize >= 3
ORDER BY visit_date
