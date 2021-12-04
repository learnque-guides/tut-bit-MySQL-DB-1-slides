# DQL - Group by clause and aggregation functions

The *GROUP BY* clause - You can use the *GROUP BY* phase to arrange the rows returned by the previous logical query processing phase in groups. The groups are determined by the elements you specify in the *GROUP BY* clause. For example, the *GROUP BY* clause in the query in Listing 2-1 has the elements *empid* and *YEAR(orderdate)*:

```sql
SELECT empid, YEAR(orderdate) FROM Sales.Orders
WHERE custid = 71
GROUP BY empid, YEAR(orderdate)
GO
```

We can use variable alias `AS` to make alias for table column name:

```sql
SELECT empid, YEAR(orderdate) AS orderyear FROM Sales.Orders
WHERE custid = 71
GROUP BY empid, YEAR(orderdate)
GO
```

The result is a number of goups of orders by year and employe id. It doesn't mean that we had 16 orders.

Let's use aggregation function *COUNT* to see how many orders was done in created groups by employe id and order year.

An aggregate function performs a calculation on multiple values and returns a single value:
* AVG - takes multiple numbers and returns the average value of the numbers,
* SUM - returns the summation of all values,
* MAX - returns the highest value,
* MIN - returns the lowest value,
* COUNT - returns the number of rows.

```sql
SELECT
  empid,
  YEAR(orderdate) AS orderyear,
  COUNT(*) AS numorders
FROM Sales.Orders
WHERE custid = 71
GROUP BY empid, YEAR(orderdate)
GO
```

Let's figure out total freigt for every group as well :)

```sql
SELECT
  empid,
  YEAR(orderdate) AS orderyear,
  SUM(freight) AS totalfreight,
  COUNT(*) AS numorders
FROM Sales.Orders
WHERE custid = 71
GROUP BY empid, YEAR(orderdate)
GO
```

If you try to refer to an attribute that does not participate in the GROUP BY clause (such as freight) and not as an input to an aggregate function in any clause that is processed after the GROUP BY clause, you get an error

```sql
SELECT empid, YEAR(orderdate) AS orderyear, freight
FROM Sales.Orders
WHERE custid = 71
GROUP BY empid, YEAR(orderdate)
GO
```

Note that all aggregate functions ignore NULLs, with one exception—COUNT(*). For example, consider a group of five rows with the values 30, 10, NULL, 10, 10 in a column called qty. The expression COUNT(*) returns 5 because there are five rows in the group, whereas COUNT(qty) returns 4 because there are four known values

```sql
SELECT empid, YEAR(orderdate) AS orderyear, freight
FROM Sales.Orders
WHERE custid = 71
GROUP BY empid, YEAR(orderdate)
GO
```
