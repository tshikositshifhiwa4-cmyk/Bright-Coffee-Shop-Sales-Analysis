SELECT *
FROM casestudy.project.bright_coffee
LIMIT 10;
---------------------------------------------------------------------------------
SELECT DISTINCT Store_Location
FROM casestudy.project.bright_coffee;
---------------------------------------------------------------------------------
SELECT DISTINCT product_category
FROM casestudy.project.bright_coffee;
---------------------------------------------------------------------------------
SELECT DISTINCT product_type
FROM casestudy.project.bright_coffee;
---------------------------------------------------------------------------------
SELECT MIN (transaction_time)
FROM casestudy.project.bright_coffee;
---------------------------------------------------------------------------------
SELECT MAX(transaction_time)
FROM casestudy.project.bright_coffee;
---------------------------------------------------------------------------------
--categorical data
SELECT store_location,
       product_category,
       product_detail,
       product_type,
       transaction_date,
       SUM(transaction_qty * unit_price) AS Revenue,
--DateTime
DAYNAME (transaction_date) AS Day_name,
CASE
    WHEN Day_name IN ('Sat', 'Sun') THEN 'Weekend'
    ELSE 'Weekday'
END AS Day_classification,
MONTHNAME (transaction_date) AS month_name,
HOUR (transaction_time) AS hour_of_day,
transaction_time,
COUNT (DISTINCT transaction_id) AS Number_of_Sales,
COUNT(DISTINCT transaction_qty) AS Total_quantity,
CASE
    WHEN transaction_time BETWEEN '06:00:00' AND '11:59:59' THEN 'Morning'
    WHEN transaction_time BETWEEN '12:00:00' AND '16:59:59' THEN 'Afternoon'
    WHEN transaction_time BETWEEN '17:00:00' AND '21:00:00' THEN 'Evening'
    END AS Time_buckets
FROM casestudy.project.bright_coffee
GROUP BY ALL;
