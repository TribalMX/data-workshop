
## Filtering records

One of the main use of SQL if to filter the columns in your result set. As an example - let's say you're only interested in extracting customer details from a table, not their subscription information as well. You're looking to filter out only the columns you're interested in.

Going back to our first query:

```SELECT * FROM customers```

returned all rows and all columns in the customer table.

What if you were only interested in looking at the records of customers located in the city of Toronto?

You'd use the following query:

``` SELECT *
    FROM customers
    WHERE city = 'Toronto';```

### How does WHERE work?

The SQL `WHERE` clause works in a plain-English way: the above querty does the same thig as `SELECT * FROM customers`, except that the results will only include rows where the `city` column equals `Toronto`.

Note this is exactly the same as filtering records in either Excel or Google Sheets!


### Using WHERE on numbers

SELECT * FROM
customers WHERE id = 232

### Conditional Logic

## Using WHERE on Text

### Grouping Conditions together







