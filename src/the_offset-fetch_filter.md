# DQL - The OFFSET-FETCH filter

The OFFSET-FETCH filter is considered an extension to the ORDER BY clause. With the OFFSET clause you indicate how many rows to skip, and with the FETCH clause you indicate how many rows to filter after the skipped rows.

```sql
SELECT orderid, orderdate, custid, empid
FROM Sales.Orders
ORDER BY orderdate, orderid
OFFSET 50 ROWS FETCH NEXT 25 ROWS ONLY
GO
```
---

```sql
SELECT orderid, orderdate, custid, empid
FROM Sales.Orders
ORDER BY orderdate, orderid
OFFSET 1 ROW FETCH NEXT 1 ROW ONLY
GO
```

Note: A query that uses OFFSET-FETCH must have an ORDER BY clause.