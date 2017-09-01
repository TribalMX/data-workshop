
# Arithmetic in SQL

You can perform arithmetic in SQL using the same operators you would in Excel: `+`, `-`, `*`, `/`. However, in SQL you can only perform arithmetic across columns on values in a given row.

This example below illustrates the user of `+`:

```SELECT
    customer_id,
    customer_first_name,
    customer_last_name,
    total_purchased_amount + total_tax_amount AS total_revenue
FROM
    customers
```

As in Excel, you can use parentheses to manage the order of operations.

if you want to add values across multiple rows, you’ll need to use aggregate functions, which are covered in a preceding session of this workshop.

> PRACTICE PROBLEMS

TODO: Add practice problems for this section





