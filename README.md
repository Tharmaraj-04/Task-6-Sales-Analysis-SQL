# Task-6-Sales-Analysis-SQL

# Online Sales Dataset

This dataset contains sample sales records for a fictional online retail platform. It is designed for SQL training tasks such as time-based sales trend analysis.

# File: `online_sales.csv`

### Columns:
- `order_id` (INT): Unique identifier for each order.
- `order_date` (DATE): The date the order was placed.
- `amount` (DECIMAL): The monetary value of the order.
- `product_id` (INT): Identifier for the product being purchased.

# Sample Data

| order_id | order_date | amount | product_id |
|----------|------------|--------|------------|
| 1        | 2024-01-15 | 120.50 | 101        |
| 2        | 2024-01-20 | 75.00  | 102        |
| ...      | ...        | ...    | ...        |

# Use Case

This dataset is intended for use with SQL databases such as PostgreSQL, MySQL, or SQLite to:
- Analyze monthly revenue trends using `SUM(amount)`
- Count the number of unique orders using `COUNT(DISTINCT order_id)`
- Extract time-based patterns with `EXTRACT(YEAR FROM order_date)` and `EXTRACT(MONTH FROM order_date)`

#  Example SQL Query

```sql
SELECT
  EXTRACT(YEAR FROM order_date) AS year,
  EXTRACT(MONTH FROM order_date) AS month,
  SUM(amount) AS total_revenue,
  COUNT(DISTINCT order_id) AS total_orders
FROM
  online_sales
GROUP BY
  EXTRACT(YEAR FROM order_date),
  EXTRACT(MONTH FROM order_date)
ORDER BY
  year,
  month;
