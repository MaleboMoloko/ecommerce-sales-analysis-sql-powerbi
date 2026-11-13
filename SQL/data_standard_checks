--check the data types
SELECT
    column_name,
    data_type
FROM
    `project-ca78f6c0-9cf8-428a-b0a.ecommerce_sales_data.INFORMATION_SCHEMA.COLUMNS`
WHERE
    table_name = 'ecommerce_sales_data_table'
ORDER BY
    ordinal_position;

-- check for nulls
SELECT
    COUNTIF(`Order Date` IS NULL) AS missing_order_date,
    COUNTIF(`Product Name` IS NULL) AS missing_product_name,
    COUNTIF(Category IS NULL) AS missing_category,
    COUNTIF(Region IS NULL) AS missing_region,
    COUNTIF(Quantity IS NULL) AS missing_quantity,
    COUNTIF(Sales IS NULL) AS missing_sales,
    COUNTIF(Profit IS NULL) AS missing_profit
FROM `project-ca78f6c0-9cf8-428a-b0a.ecommerce_sales_data.ecommerce_sales_data_table`;

--check for duplicates
SELECT
    SUM(record_count - 1) AS duplicate_records
FROM (
    SELECT
        COUNT(*) AS record_count
    FROM `project-ca78f6c0-9cf8-428a-b0a.ecommerce_sales_data.ecommerce_sales_data_table`
    GROUP BY
        `Order Date`,
        `Product Name`,
        Category,
        Region,
        Quantity,
        Sales,
        Profit
    HAVING COUNT(*) > 1
);

