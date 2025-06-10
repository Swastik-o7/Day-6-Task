# Day-6-Task
-- Monthly Sales Trend Analysis: Revenue and Order Volume

SELECT 
    EXTRACT(YEAR FROM date) AS order_year,
    EXTRACT(MONTH FROM date) AS order_month,
    SUM(amount) AS total_revenue,
    COUNT(DISTINCT order_id) AS order_volume
FROM 
    order_a
WHERE 
    date >= '2023-01-01' AND date < '2024-01-01'  -- Example: filter for the year 2023
GROUP BY 
    EXTRACT(YEAR FROM date), 
    EXTRACT(MONTH FROM date)
ORDER BY 
    order_year,
    order_month;
