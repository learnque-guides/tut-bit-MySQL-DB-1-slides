# CASE expression

A *CASE* expression is a scalar expression that returns a value based on conditional logic. 

```sql
SELECT productid, productname, categoryid,
  CASE categoryid
    WHEN 1 THEN 'Beverages'
    WHEN 2 THEN 'Condiments'
    WHEN 3 THEN 'Confections'
    WHEN 4 THEN 'Dairy Products'
    WHEN 5 THEN 'Grains/Cereals'
    WHEN 6 THEN 'Meat/Poultry'
    WHEN 7 THEN 'Produce'
    WHEN 8 THEN 'Seafood'
    ELSE 'Unknown Category'
  END AS categoryname
FROM Production.Products
GO
```

```sql
SELECT orderid, custid, val,
  CASE
    WHEN val < 1000.00                   THEN 'Less than 1000'
    WHEN val BETWEEN 1000.00 AND 3000.00 THEN 'Between 1000 and 3000'
    WHEN val > 3000.00                   THEN 'More than 3000'
    ELSE 'Unknown'
  END AS valuecategory
FROM Sales.OrderValues
GO
```

Note: T-SQL supports some functions you can consider as abbreviations of the *CASE* expression: *ISNULL*, *COALESCE*, *IIF*, and *CHOOSE*. Note that of the four, only *COALESCE* is standard.
