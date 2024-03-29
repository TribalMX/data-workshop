# SQL SUM function

SUM is a SQL aggregate function that totals the values in a given column. Unlike COUNT, you can only use SUM on columns containing numerical values.

The query below selects the sum of the volume column from the Apple stock prices dataset:

```SELECT SUM(volume)
  FROM tutorial.aapl_historical_stock_price```

An important thing to remember: aggregators only aggregate vertically. If you want to perform a calculation across rows, you would do this with simple arithmetic.

You don’t need to worry as much about the presence of nulls with SUM as you would with COUNT, as SUM treats nulls as 0.

