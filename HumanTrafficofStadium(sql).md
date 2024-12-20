~~~~mysql
-- Step 1: Filter rows where 'people >= 100' and assign a GroupID to consecutive rows
WITH FilteredStadium AS (
    SELECT 
        *, 
        -- GroupID is calculated as the difference between 'id' and the row number
        id - ROW_NUMBER() OVER (ORDER BY id ASC) AS GroupID
    FROM 
        Stadium
    WHERE 
        people >= 100
),

-- Step 2: Count the number of rows in each group (GroupID)
GroupedStadium AS (
    SELECT 
        *, 
        -- GroupSize represents the total number of rows in each group
        COUNT(GroupID) OVER (PARTITION BY GroupID) AS GroupSize
    FROM 
        FilteredStadium
)

-- Step 3: Select rows from groups with at least 3 rows
SELECT 
    id, 
    visit_date, 
    people
FROM 
    GroupedStadium
WHERE 
    GroupSize >= 3 -- Keep groups with 3 or more rows
ORDER BY 
    visit_date; -- Sort the results by visit_date
