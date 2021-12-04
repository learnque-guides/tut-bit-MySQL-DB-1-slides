# DQL - The TOP filter

The TOP filter is a proprietary T-SQL feature you can use to limit the number or percentage of rows your query returns. It relies on two elements as part of its specification: one is the number or percent of rows to return, and the other is the ordering.

```sql
SELECT TOP (5) orderid, orderdate, custid, empid
FROM Sales.Orders
ORDER BY orderdate DESC
GO
```

Note: *ORDER BY* clause is evaluated after the *SELECT* clause, which includes the *DISTINCT* option. The same is true with the *TOP* filter, which relies on the *ORDER BY* specification to give it its filtering-related meaning. This means that if *DISTINCT* is specified in the *SELECT* clause, the *TOP* filter is evaluated after duplicate rows have been removed.

You can use the TOP option with the PERCENT keyword, in which case SQL Server calculates the number of rows to return based on a percentage of the number of qualifying rows, rounded up.

```sql
SELECT TOP (1) PERCENT orderid, orderdate, custid, empid
FROM Sales.Orders
ORDER BY orderdate DESC;
```