
## Filtering records

One of the main use of SQL if to filter the columns in your result set. As an example - let's say you're only interested in extracting customer demographics from a table, not their subscription information as well. You're can start to filter out only the columns you're interested in.

Going back to our first query:

```SELECT * FROM customers```

returned all rows and all columns in the customer table.

What if you were only interested in looking at the records of customers located in the city of Toronto?

You'd use the following query:

``` SELECT *
    FROM customers
    WHERE city = 'Toronto';```

### How does WHERE work?

The SQL `WHERE` clause works in a plain-English way: the above query does the same thig as `SELECT * FROM customers`, except that the results will only include rows where the `city` column equals `Toronto`.

Note this is exactly the same as filtering records in either Excel or Google Sheets!


## Filtering columns

We can also use SQL to only look at specific columns in the table. As an example, let's say that you're working as a marketer for the company, and you need the email addresses of all customers who live in Toronto. You can modify the query above as follows:

``` SELECT customerid, email_address
    FROM customers
    WHERE city = 'Toronto'```

### Filtering numerical data

The most basic way to filter data is using comparison operators.
TODO: insert image of the different types of comparison operators

Most of these comparison operators apply to numerical columns. For example, in order to figure out which customers had purchased quantities greater than $100, we would use the following query:

```SELECT * FROM
customers WHERE total_purchases > 100```

### Filtering non-numerical data

We can also use conditional operators on non-numerical data, such as text.




### Conditional Logic


### Grouping Conditions together







