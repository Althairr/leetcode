~~~~mysql
# Write your MySQL query statement below
SELECT id,
    MAX(IF(month = 'Jan', revenue, NULL)) AS Jan_revenue,
    MAX(IF(month = 'Feb', revenue, NULL)) AS Feb_revenue,
    MAX(IF(month = 'Mar', revenue, NULL)) AS Mar_revenue,
    MAX(IF(month = 'Apr', revenue, NULL)) AS Apr_revenue,
    MAX(IF(month = 'May', revenue, NULL)) AS May_revenue,
    MAX(IF(month = 'Jun', revenue, NULL)) AS Jun_revenue,
    MAX(IF(month = 'Jul', revenue, NULL)) AS Jul_revenue,
    MAX(IF(month = 'Aug', revenue, NULL)) AS Aug_revenue,
    MAX(IF(month = 'Sep', revenue, NULL)) AS Sep_revenue,
    MAX(IF(month = 'Oct', revenue, NULL)) AS Oct_revenue,
    MAX(IF(month = 'Nov', revenue, NULL)) AS Nov_revenue,
    MAX(IF(month = 'Dec', revenue, NULL)) AS Dec_revenue
FROM Department
GROUP BY id;


~~~~
