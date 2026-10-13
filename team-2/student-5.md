# Debugging Tips (SQL)

Jake Jimenez (student-5)

# Tip 1: Build your query in steps and check the output each time

Use the output as a friend. Start with just the columns you want in your `SELECT`, then add your `JOIN` (deciding which type you need) and run it. Checking the result after each step shows how the table is changing and whether you're on the right path. Keep going the same way for `WHERE`, `GROUP BY`, and so on.

# Example 

```sql
-- Step 1: check the base table
SELECT customer_id, name
FROM customers;

-- Step 2: add the join, run again. Did the row count jump unexpectedly?
SELECT c.customer_id, c.name, o.order_id, o.total
FROM customers c
LEFT JOIN orders o ON c.customer_id = o.customer_id;

-- Step 3: add the filter and grouping only after the join looks right
SELECT c.customer_id, c.name, SUM(o.total) AS total_spent
FROM customers c
LEFT JOIN orders o ON c.customer_id = o.customer_id
WHERE o.total > 0
GROUP BY c.customer_id, c.name;
```

If the numbers in Step 3 look wrong, you know to look back at Step 2 instead of debugging the whole query at once.

## Tip 2: Plan the result before writing the query

Don't start writing the query right away. First decide what you want the final result to look like: which columns, one row per what, and which tables you need. Thinking it through first leads to fewer bugs later.

**Example:** "I want one row per customer with their total spending." That tells you that you need `customers` and `orders`, a join on `customer_id`, `SUM(total)`, and `GROUP BY` customer.