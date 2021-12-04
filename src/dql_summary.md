# DQL - Summary

To put it all together, the following list presents the logical order in which all clauses discussed so far are processed:

* FROM
* WHERE
* GROUP BY
* HAVING
* SELECT
  * Expressions
  * DISTINCT
* ORDER BY
  * TOP/OFFSET-FETCH

Note: It is possible to use some arithmetic operator in *SELECT Expersion*

```sql
SELECT orderid, productid, qty, unitprice, discount,
  qty * unitprice * (1 - discount) AS val
FROM Sales.OrderDetails;
```

When multiple operators appear in the same expression, SQL Server evaluates them based on operator precedence rules. The following list describes the precedence among operators, from highest to lowest:

1. ( ) (Parentheses)
2. * (Multiplication), / (Division), % (Modulo)
3. + (Positive), – (Negative), + (Addition), + (Concatenation), – (Subtraction)
4. =, >, <, >=, <=, <>, !=, !>, !< (Comparison operators)
5. NOT
6. AND
7. BETWEEN, IN, LIKE, OR
8. = (Assignment)