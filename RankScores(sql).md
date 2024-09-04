~~~~mysql
-- ensure there are no gaps between the rank using DENSE_RANK()
SELECT score, DENSE_RANK() OVER (ORDER BY score DESC) AS "rank"
FROM Scores
