# First SQL Query

Type in the following statement into the console:

``` SELECT * FROM customers ```

# What actually happens when you run a query?



# Conventions

You may have noticed that the `SELECT` and `FROM` commands are capitalized. This isn't actually necessary - SQL will understand these commands if you type them in lowercase. Capitalizing commands is simply a convention that makes queries easier to read. Similarly, SQL treats one space, multiple spaces, or a line break as being the same thing.

While most capitalization conventions are the same, there are several conventions for formatting line breaks. You'll pick up on several of these in the tutorial.

TODO: Insert link to SQL code best practices


# SQL Basics

# The LIMIT Clause

In the SQL Editor, try this query:

```SELECT * FROM customers LIMIT 100```

As you might expect, the limit restricts how many rows the SQL query returns.

## When do you need to limit your results?

Many analysts use limits as a simple way to keep their queries from taking too long to return. The aim of many of your queries will simply be to see what a particular table looks like -- you'll want to scan the first few rows of data to get an idea of which fields you care about and how you want to manipulate them. If you query a very large table and don't use a limit, you could end up waiting a long time for all of your results to be displayed, which doesn't make sense if you only care about the first few.

