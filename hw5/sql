-- 1
SELECT
    date,
    amount,
    SUM(amount) OVER (ORDER BY date) AS cumulative_amount
FROM
transactions;

--2
SELECT
    id,
    category,
    price,
    price - avg_price_category AS price_deviation
FROM (
    SELECT
        id,
        category,
        price,
        AVG(price) OVER (PARTITION BY category) AS avg_price_category
    FROM
        products
) AS subquery;

--3
SELECT
    log_time,
    temperature,
    AVG(temperature) OVER (ORDER BY log_time ASC ROWS BETWEEN 2 PRECEDING AND CURRENT ROW) AS rolling_avg
FROM
    temperature_logs;

--4
SELECT
    project_id,
    MIN(start_date) AS first_task_start_date,
    MAX(start_date) AS last_task_start_date
FROM
    project_tasks
GROUP BY
    project_id;
