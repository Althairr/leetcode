~~~~mysql
# Brute force
SELECT id, "Root" AS type 
FROM Tree
WHERE p_id IS NULL

UNION

SELECT id, "Inner" AS type
From Tree t
WHERE t.p_id AND t.id IN (
    SELECT p_id AS id
    FROM Tree
    WHERE p_id 
    GROUP BY p_id
)

UNION

SELECT id, "Leaf" AS type 
from Tree t 
WHERE NOT EXISTS (
    SELECT 1 
    fROM tree 
    WHERE p_id = t.id 
)
    AND p_id IS NOT NULL;

# Below this is the another way
SELECT id,
    CASE 
        WHEN p_id IS NULL THEN 'Root'
        WHEN id IN (SELECT p_id FROM Tree)THEN 'Inner'
        ELSE 'Leaf'
        END AS type
FROM Tree;
		
