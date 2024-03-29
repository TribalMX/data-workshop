# The SQL MIN and MAX functions

MIN and MAX are SQL aggregation functions that return the lowest and highest values in a particular column.

They’re similar to COUNT in that they can be used on non-numerical columns. Depending on the column type, MIN will return the lowest number, earliest date, or non-numerical value as close alphabetically to “A” as possible. As you might suspect, MAX does the opposite—it returns the highest number, the latest date, or the non-numerical value closest alphabetically to “Z.”

For example, the following query selects the MIN and the MAX from the numerical volume column in the customer dataset.

```
SELECT MIN(volume) AS min_volume,
       MAX(volume) AS max_volume
  FROM tutorial.aapl_historical_stock_price
```

## SQL AVG

