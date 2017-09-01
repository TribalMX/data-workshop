# SQL Logical operators

In the previous lesson, you played with some comparison operators to filter data. You’ll likely also want to filter data using several conditions—possibly more often than you’ll want to filter by only one condition. Logical operators allow you to use multiple comparison operators in one query.

Each logical operator is a special snowflake, so we’ll go through them individually in the following lessons. Here’s a quick preview:

- `LIKE` allows you to match similar values, instead of exact values.
- `IN` allows you to specify a list of values you’d like to include.
- `BETWEEN` allows you to select only rows within a certain range.
- `IS NULL` allows you to select rows that contain no data in a given column.
- `AND` allows you to select only rows that satisfy two conditions.
- `OR` allows you to select rows that satisfy either of two conditions.
- `NOT` allows you to select rows that do not match a certain condition.

## SQL LIKE

`LIKE` is a logical operator in SQL that allows you to match on similar values rather than exact ones.

Run the code to see which results are returned.

```SELECT *
  FROM lighthouselabs.customer_purchases
 WHERE "item" LIKE 'Roomba%'```

### Wildcards and ILIKE

The % used above represents any character or set of characters. In this case, % is referred to as a “wildcard.” In the type of SQL that Mode uses, LIKE is case-sensitive, meaning that the above query will only capture matches that start with a capital “R” and lower-case “oomba.” To ignore case when you’re matching values, you can use the ILIKE command:

```SELECT *
  FROM lighthouselabs.customer_purchases
 WHERE "item" ILIKE 'roomba'```

> PRACTICE PROBLEMS

## SQL IN

IN is a logical operator in SQL that allows you to specify a list of values that you’d like to include in the results. For example, the following query of data from the `customers` table will return results for which the year_rank column is equal to one of the values in the list:

```SELECT *
  FROM lighthouselabs.customers
 WHERE year_rank IN (1, 2, 3)```

As with comparison operators, you can use non-numerical values, but they need to go inside single quotes. Regardless of the data type, the values in the list must be separated by commas. Here’s another example:

```SELECT *
  FROM tutorial.billboard_top_100_year_end
 WHERE artist IN ('Taylor Swift', 'Usher', 'Ludacris')```

> PRACTICE PROBLEMS

## SQL BETWEEN


BETWEEN is a logical operator in SQL that allows you to select only rows that are within a specific range. It has to be paired with the AND operator, which you’ll learn about in a later lesson. Here’s what BETWEEN looks like on a Billboard Music Charts dataset:

```SELECT *
  FROM tutorial.billboard_top_100_year_end
 WHERE year_rank BETWEEN 5 AND 10```


## The IS NULL operator

IS NULL is a logical operator in SQL that allows you to exclude rows with missing data from your results.

Some tables contain null values—cells with no data in them at all. This can be confusing for heavy Excel users, because the difference between a cell having no data and a cell containing a space isn’t meaningful in Excel. In SQL, the implications can be pretty serious. This is covered in greater detail in the intermediate tutorial, but for now, here’s what you need to know:

You can select rows that contain no data in a given column by using IS NULL. Let’s try it out using a dataset from the `customers` table.

```SELECT *
  FROM lighthouselabs.customers
 WHERE country IS NULL```

## SQL AND

AND is a logical operator in SQL that allows you to select only rows that satisfy two conditions. Using data from the Billboard Music Charts, the following query will return all rows for top-10 recordings in 2012.

```SELECT *
  FROM tutorial.billboard_top_100_year_end
 WHERE year = 2012 AND year_rank <= 10```

> PRACTICE PROBLEMS

## SQL OR

OR is a logical operator in SQL that allows you to select rows that satisfy either of two conditions. It works the same way as AND, which selects the rows that satisfy both of two conditions. Try OR out by running this query against data from the Billboard Music Charts:

```SELECT *
  FROM tutorial.billboard_top_100_year_end
 WHERE year_rank = 5 OR artist = 'Gotye'```



## SQL NOT

NOT is a logical operator in SQL that you can put before any conditional statement to select rows for which that statement is false.

Here’s what NOT looks like in action in a query of Billboard Music Charts data:

```SELECT *
  FROM lighthouselabs.customers
 WHERE year = 2013
   AND year_rank NOT BETWEEN 2 AND 3```

## SQL ORDER BY

Once you’ve learned how to filter data, it’s time to learn how to sort data. The ORDER BY clause allows you to reorder your results based on the data in one or more columns. First, take a look at how the table is ordered by default:

Now let’s see what happens when we order by one of the columns:

```SELECT *
  FROM tutorial.billboard_top_100_year_end
 ORDER BY artist
```

### Ordering data by multiple columns

You can also order by mutiple columns. This is particularly useful if your data falls into categories and you’d like to organize rows by date, for example, but keep all of the results within a given category together. This example query makes the most recent years come first but orders top-ranks songs before lower-ranked songs:

```SELECT *
  FROM tutorial.billboard_top_100_year_end
  WHERE year_rank <= 3
 ORDER BY year DESC, year_rank```

### Using comments


